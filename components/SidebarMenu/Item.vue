<template>
  <div 
    :class="[{'first-item' : firstItem}, {'open-item' : show}, {'active-item' : active}]" 
    class="vsm-item" 
    @mouseenter="mouseEnter($event)">
    <template v-if="isRouterLink">
      <router-link 
        :to="item.href" 
        class="vsm-link" 
        @click.native="clickEvent">
        <i 
          v-if="item.icon" 
          :class="item.icon"
          class="vsm-icon" />
        <template v-if="!isCollapsed">
          <span class="vsm-title">{{ item.title }}</span>
          <i 
            v-if="item.child" 
            :class="{'open-arrow' : show}"
            class="vsm-arrow" />
        </template>
      </router-link>
    </template>
    <template v-else>
      <a 
        :href="!item.child ? item.href : '#'" 
        class="vsm-link" 
        @click="clickEvent">
        <i 
          v-if="item.icon" 
          :class="item.icon"
          class="vsm-icon" />
        <template v-if="!isCollapsed">
          <span class="vsm-title">{{ item.title }}</span>
          <i 
            v-if="item.child" 
            :class="{'open-arrow' : show}"
            class="vsm-arrow" />
        </template>
      </a>
    </template>
    <div 
      v-if="!isCollapsed && item.child"
      class="vsm-dropdown" >
      <transition name="show-animation">
        <div 
          v-if="show"
          class="vsm-list"> 
          <sub-item 
            v-for="(subItem, index) in item.child" 
            :item="subItem" 
            :key="index" />
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
import SubItem from '@/components/SidebarMenu/SubItem.vue'
import { itemMixin } from '@/components/SidebarMenu/mixin'

export default {
  components: {
    SubItem
  },
  mixins: [itemMixin],
  props: {
    item: {
      type: Object,
      required: true
    },
    firstItem: {
      type: Boolean,
      default: false
    }
    // isCollapsed: {
    //   type: Boolean
    // }
  },
  data() {
    return {
      show: false
    }
  },
  created() {
    if (this.firstItem) {
      this.$parent.$on('collapse', this.closeDropdown)
    }
  },
  methods: {
    mouseEnter(event) {
      if (this.isCollapsed && this.firstItem) {
        this.$parent.$emit('mouseEnterItem', {
          item: this.item,
          pos:
            event.currentTarget.getBoundingClientRect().top -
            this.$parent.$el.getBoundingClientRect().top,
          height: this.$el.offsetHeight
        })
      }
    }
  }
}
</script>

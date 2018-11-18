<template>
  <div 
    :class="[{'open-item' : show}, {'active-item' : active}]"
    class="vsm-item" >
    <template v-if="isRouterLink">
      <router-link 
        :to="item.href" 
        class="vsm-link"
        @click.native="clickEvent" >
        <i 
          v-if="item.icon" 
          :class="item.icon"
          class="vsm-icon" />
        <span class="vsm-title">{{ item.title }}</span>
        <i 
          v-if="item.child" 
          :class="{'open-arrow' : show}"
          class="vsm-arrow" /> 
      </router-link>
    </template>
    <template v-else>
      <a 
        :href="!item.child ? item.href : '#'" 
        :class="{'active' : isLinkActive}"
        class="vsm-link"
        @click="clickEvent" >
        <i 
          v-if="item.icon" 
          :class="item.icon"
          class="vsm-icon" />
        <span class="vsm-title">{{ item.title }}</span>
        <i 
          v-if="item.child" 
          :class="{'open-arrow' : show}"
          class="vsm-arrow" /> 
      </a>
    </template>
    <div 
      v-if="item.child"
      class="vsm-dropdown" >
      <transition name="show-animation">
        <div 
          v-if="show"
          class="vsm-list" >
          <item 
            v-for="(subItem, index) in item.child" 
            :item="subItem" 
            :key="index" />
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
import Item from '@/components/SidebarMenu/Item.vue'
import { itemMixin } from '@/server/mixin'

export default {
  components: {
    Item
  },
  mixins: [itemMixin],
  // props: {
  //   item: Object,
  // },
  data() {
    return {
      show: false
    }
  },
  beforeCreate() {
    this.$options.components.Item = require('@/components/SidebarMenu/Item.vue').default
  }
}
</script>

<template>
  <div 
    v-if="item"
    :class="[{'open-item' : item.child}, {'active-item' : active}]"
    class="vsm-item mobile-item" >
    <router-link 
      v-if="isRouterLink" 
      :to="item.href"
      class="vsm-link" > 
      {{ item.title }}
      <i 
        v-if="item.child" 
        :class="{'open-arrow' : show}"
        class="vsm-arrow" />
    </router-link>
    <a 
      v-else-if="item" 
      :href="!item.child ? item.href : '#'" 
      class="vsm-link"
      @click="clickEvent" >
      { {item.title }}
      <i 
        v-if="item.child" 
        :class="{'open-arrow' : item.child}"
        class="vsm-arrow" />
    </a>
  </div>
</template>

<script>
import SubItem from '@/components/SidebarMenu/SubItem.vue'
import { itemMixin } from '@/server/mixin'

export default {
  components: {
    SubItem
  },
  mixins: [itemMixin],
  // props: {
  //   item: {
  //     type: Object
  //   }
  // },
  watch: {
    item() {
      this.active = this.isLinkActive()
    }
  }
}
</script>

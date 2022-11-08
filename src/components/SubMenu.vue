<template>
  <div class="sub-menu">
    <div v-for="category in menu" :key="category.cat_slug">
        <SubMenuItem :parentSlug="this.parentSlug" :category="category" />
    </div>
  </div>
</template>

<script>
import SubMenuItem from './SubMenuItem.vue'

export default {
  name: 'SubMenu',
  props:{
    menu: Array,
    parentSlug: String
  },
  components:{
    SubMenuItem
  },
}
</script>

<style scoped>
.sub-menu{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    padding: 0px 100px;
}
</style>
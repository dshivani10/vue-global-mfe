<template>
  <div class="sub-menu-item">
    <p @click="navigateCat(category.cat_slug)" class="sub-menu-name">{{category.cat_name}}</p>
    <div v-if="category.sub_cats.length">
        <div v-for="cat in category.sub_cats" :key="cat.sub_cat_slug">
            <p @click="navigateSubCat(category.cat_slug,cat.sub_cat_slug)" class="sub-cat-name">{{cat.sub_cat_name}}</p>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SubMenuItem',
  props:{
    category: Object,
    parentSlug: String
  },
  methods:{
    navigateCat(slug){
      this.$router.push(`/products/${this.parentSlug}/${slug}`)
    },
    navigateSubCat(cat,sub){
      this.$router.push(`/products/${this.parentSlug}/${cat}/${sub}`)
    }
  }
}
</script>

<style scoped>
.sub-menu-item{
    text-align: left;
    font-size: 14px;
    padding: 20px 0 40px 0;
}
.sub-menu-name{
    font-weight: 700;
    cursor: pointer;
}
.sub-menu-name:hover{
    text-decoration: underline;
}
.sub-cat-name{
    margin: 5px 0;
    cursor: pointer;
}
.sub-cat-name:hover{
    text-decoration: underline;
}
</style>
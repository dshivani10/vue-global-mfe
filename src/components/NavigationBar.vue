<template>
    <div>
        <div class="ecom-navbar">
            <div v-for="item in navlist" :key="item.slug">
                <NavigationItem @click="navigate(item.slug)" @mouseenter="selectNavSlug(item.slug)" @mouseleave="resetNavSlug" :item="item.name"/>
            </div>
        </div>
        <div class="ecom-nav-menu">
            <div v-for="item in navlist" :key="item.slug">
                <SubMenu @mouseenter="selectHoveredSlug(item.slug)" @mouseleave="resetHoveredSlug" v-show="this.hoveredMenuSlug === item.slug || this.navSlug === item.slug" :parentSlug="item.slug" :menu="item.categories" />
            </div>
        </div>
    </div>
</template>
<script>
import NavigationItem from './NavigationItem.vue'
import SubMenu from './SubMenu.vue';

export default {
    name: 'NavigationBar',
    props:{
        navlist: Array
    },
    data(){
        return{
            hoveredMenuSlug:'',
            navSlug:'',
        }
    },
    components: {
        NavigationItem,
        SubMenu
    },
    methods:{
        navigate(slug){
            this.$router.push(`/products/${slug}`)
        },
        selectNavSlug(slug){
            this.navSlug = slug
        },
        resetNavSlug(){
            this.navSlug = ''
        },
        selectHoveredSlug(slug){
            this.hoveredMenuSlug = slug
        },
        resetHoveredSlug(){
            this.hoveredMenuSlug = ''
        }
    }
}
</script>
<style scoped>
    .ecom-navbar{
        background-color: #a4c0c4;
        display: flex;
        justify-content: center;
    }
    .ecom-nav-menu{
        position: absolute;
        width: 100%;
        background-color: #f5f5dc;
    }
</style>
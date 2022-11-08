<template>
    <div class="ecom-navbar">
        <div v-for="item in navlist" :key="item.slug">
            <NavigationItem @click="navigate(item.slug)" :item="item.name"/>
        </div>
    </div>
</template>
<script>
import NavigationItem from './NavigationItem.vue'

export default {
    name: 'NavigationBar',
    props:{
        navlist: Array
    },
    components: {
        NavigationItem
    },
    methods:{
        navigate(slug){
            this.$router.push(`/products/${slug}`)
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
</style>
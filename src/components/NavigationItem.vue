<template>
    <div class="ecom-navitem">
        <div class="ecom-navtitle">
            <p class="nav-title">{{item}}</p>
        </div>
    </div>
</template>
<script>
export default {
    name: 'NavigationItem',
    props: {
        item: String
    },
}
</script>
<style scoped>
    .ecom-navtitle{
        padding: 10px 40px;
        border-bottom: 2px solid transparent;
        cursor: pointer;
    }
    .ecom-navtitle:hover{
        border-bottom: 2px solid #4f686b;
    }
    .nav-title{
        margin: 0;
        font-size: 15px;
        pointer-events: none;
        font-weight: 500;
    }
</style>
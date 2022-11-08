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
        padding: 10px 20px;
        border-bottom: 2px solid transparent;
        cursor: pointer;
    }
    .ecom-navtitle:hover{
        border-bottom: 2px solid #4f686b;
    }
    .nav-title{
        margin: 0;
        font-size: 14px;
        pointer-events: none;
    }
</style>
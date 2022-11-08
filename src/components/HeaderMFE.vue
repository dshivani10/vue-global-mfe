<template>
  <div class="header-mfe">
    <h1 @click="navigateHome" class="header-title">{{title}}</h1>
  </div>
</template>

<script>
export default {
  name: 'HeaderMFE',
  props:{
    title:String
  },
  methods:{
    navigateHome(){
      this.$router.push('/');
    }
  }
}
</script>
<style scoped>
.header-title{
  font-size: 50px;
  font-family: monospace;
  padding: 20px 0px;
  margin: 0;
  cursor: pointer;
}
</style>
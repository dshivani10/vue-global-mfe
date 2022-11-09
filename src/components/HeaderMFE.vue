<template>
  <div class="header-mfe">
    <h1 @click="navigate('')" class="header-title">{{title}}</h1>
    <div class="icons-container">
      <div>
        <span v-if="wishlist_count" class="logo-number">{{wishlist_count}}</span>
        <img @click="navigate('user/wishlist')" class="logo-icon" src="../assets/heart.png" alt="wishlist icon">
      </div>
      <div>
        <span v-if="cart_count" class="logo-number">{{cart_count}}</span>
        <img @click="navigate('user/cart')" class="logo-icon" src="../assets/cart.png" alt="cart icon" />
      </div>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex';

export default {
  name: 'HeaderMFE',
  props:{
    title:String
  },
  computed:{
    ...mapState(['wishlist_count','cart_count'])
  },
  methods:{
    navigate(val){
      this.$router.push(`/${val}`);
    },
  },
}
</script>

<style scoped>
.header-mfe{
  display: flex;
  align-items: center;
}
.header-title{
  font-size: 50px;
  font-family: monospace;
  padding: 20px 0px;
  margin: 0;
  cursor: pointer;
  width: 100%;
}
.icons-container{
  position: absolute;
  right: 15px;
  display: flex;
}
.logo-icon{
  height: 40px;
  margin: 10px;
  cursor: pointer;
}
.logo-number{
  position: absolute;
  background: black;
  color: white;
  height: 20px;
  width: 20px;
  border-radius: 50%;
  font-size: 11px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
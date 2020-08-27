<template>
  <div id="app">
    <loading :active.sync="isLoading"></loading>
    <div id="nav">
      <router-link to="/">首頁</router-link> |
        <router-link to="/products">產品列表</router-link> |
        <router-link to="/cart">購物車</router-link> |
        <router-link to="/about">關於我們</router-link> |
        <router-link to="/checkout">結帳</router-link> |
        <router-link to="/checkouted">結帳完成</router-link> |
        <router-link to="/contact">聯絡我們</router-link>
    </div>
    <router-view />
  </div>
</template>

<script>
export default {
  data () {
    return {
      isLoading: false
    }
  },
  mounted () {
    this.isLoading = true
    setTimeout(() => {
      this.isLoading = false
    }, 2000)
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>

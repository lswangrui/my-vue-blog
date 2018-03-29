<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* background-image: url('@/assets/css/images/car.jpg') */
}
</style>
<script>
  import './assets/css/reset.css';//引入基础样式重置表
  import './assets/font/iconfont.css';

  export default {
    data() {
      return {
        bg:{}
      }
    },
    // components: {
    //   Name
    // },
  }
</script>

<template>
  <div>
    <input type="button" value="发送" @click="getData">
  </div>
</template>

<script>
  import axios from 'axios';
  export default {
    data() {
      return {
        list: []
      }
    },
    computed: {
      name() {
        return this.data
      }
    },
    methods: {
      getData() {
        axios.get('/string').then((response) => {
          let res = response.data;
          console.log(res)
        })
      }
    },
  }
</script>

<style scoped>

</style>

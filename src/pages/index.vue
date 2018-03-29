<template>
  <div class="main" :style="bg">
    <div class="mask">
      <top-nav :nowIndex='0'></top-nav>
      <section class="container">
        这里是主题内容
      </section>
      <bottom-link></bottom-link>
    </div>

  </div>
</template>

<script>
  import axios from 'axios'
  import topNav from '../components/topNav'
  import bottomLink from '../components/bottomLink'
  export default {
    data() {
      return {
        weather: {},
        url: '/open/api/weather/json.shtml?city=青岛',
        bg:{


        }
      }
    },
    mounted() {
      this.getCity()
      // this.getWeather()
    },
    methods: {
      getCity(){
        axios({
          method:'get',
          url:'http://iploc.market.alicloudapi.com/v3/ip',
          headers: {'Authorization': 'APPCODE fa0ee23e57c447d3af73f4f79a309e83'},
        }).then(response=>{
          let res = response.data;
          console.log(res)
        })
      },
      getWeather() {
        let url = encodeURI(this.url)
        axios.get('/weather' + url).then(response => {
          let res = response.data;
          console.log(res);
        })
      },
    },
    components:{
      topNav,
      bottomLink
    }
  }
</script>

<style scoped>
  .main {
    max-height: 949px;
    max-width: 1920px;
    /* height: 80px; */
    line-height: 80px;

    background-image: url("/static/images/bg.jpg");
    background-repeat: no-repeat;
    background-size:100% 100%;
  }
  .container {
    height: 699px;
  }
  .mask{
    background-color: rgba(51, 51, 51, 0.3);
  }

</style>

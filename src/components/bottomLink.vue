<template>
  <div>
    <footer class="footerNav">
      <div class="moreLink">
        <div class="linkLeft">
          <ul>
            <a href="javascript:;">友情链接</a>
            <a href="http://www.baidu.com" target="_blank">百度</a>
            <a href="http://www.baidu.com" target="_blank">google</a>
            <a href="http://www.baidu.com" target="_blank">facebook</a>
            <a href="http://www.baidu.com" target="_blank">1111</a>
          </ul>
        </div>
        <div class="linkRight">
          <p>
            <img src="/static/images/GitHub.png" alt="">
            <a href="#">wangrui</a>
            <img src="/static/images/email.png" alt="" style="margin-left:20px;">
            <a href="#">410669943@qq.com</a>
          </p>
        </div>
      </div>
      <div class="siteInfo">
        <p>Copyright ©  2017 -- {{nowYear}} by  {{auth}}</p>
        <p>苏ICP备14036269号-1</p>

      </div>
    </footer>
  </div>
</template>

<script>
export default {
  data () {
    return {
       auth: 'wangrui',
    }
  },
   computed: {
    nowYear() {
      return new Date().getFullYear();
    }
  },
}
</script>
<style scoped>
.footerNav {
    margin-top: 50px;
    color: #fff;
    /* background-color: rgba(51, 51, 51, 0.3) */
  }

  .linkLeft {
    width: 59%;
    display: inline-block;
  }

  .linkLeft a {
    color: #fff;
    padding: 5px;
    text-decoration: none;
  }


  /* .linkLeft a:not(:first-child):hover{
    text-decoration: none;
    border-bottom: 2px solid #fff;
  } */

  .linkRight {
    width: 40%;
    display: inline-block;
    /* border-left: 2px solid #fff; */
  }

  .linkRight a {
    color: #fff;
    text-decoration: none;
  }

  .linkRight img {
    width: 20px;
    vertical-align: middle;
  }

  .siteInfo {
    line-height: 20px;
    /* background-color: rgba(34, 34, 34, 0.5); */
  }
</style>

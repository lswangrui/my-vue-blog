<template>
  <div class="main">
    <div class="mask">
      <top-nav :nowIndex='4' class="b-topNav"></top-nav>
      <section class="container">
        <div class="artContainer">
          <div>

          </div>
        </div>
        <div class="rightBanner">
          <div class="goSearch">
            <input type="text" id="searchTxt" placeholder="查询">
            <i class="icon iconfont icon-search"></i>
          </div>
          <div class="contact">
            <h1>CATEGORY</h1>
            <ul>
              <li v-for="item in category" :key='item.index'>
                <span>{{item.num}}</span>
                <a :href="item.url">{{item.title}}</a>
              </li>
            </ul>
          </div>
          <div class="tags">
            <h1>TAGS</h1>
            <ul>
              <li  v-for="item in tags" :key='item.index'>
                <a class="tags-btn" href="item.url">{{item.title}}</a>
              </li>
            </ul>
          </div>
          <div class="newArt">
            <h1>ARTICLE</h1>
            <ul>
              <li v-for="item in artList" :key="item.index">
                <a href="#" class="artPic">
                  <img src="/static/images/taiji.png" alt="">
                </a>
                <div class="introduce">
                  <p class="art-title">{{item.title}}</p>
                  <p><i class="icon iconfont icon-shijianriqi"></i>{{item.data}} &nbsp;&nbsp;<i class="icon iconfont icon-liulan"></i>{{item.visited}}</p>
                </div>

              </li>
            </ul>
          </div>

        </div>
      </section>
      <bottom-link class="b-bottomLink"></bottom-link>
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
        category: [
          {
            title:'WDMCJSJJSNA',
            url:'/',
            num:15
          },
          {
            title:'WEQEQWASD',
            url:'/',
            num:17
          },
          {
            title:'FGJFHFGH',
            url:'/',
            num:9
          },
          {
            title:'MNBVBNCJGJ',
            url:'/',
            num:56
          },
          {
            title:'CVNBTUYRTY',
            url:'/',
            num:8
          },
        ],
        tags:[
          {
            url:'/',
            title:'wepack'
          },
           {
            url:'/',
            title:'javascript'
          },
           {
            url:'/',
            title:'vue2'
          },
           {
            url:'/',
            title:'git'
          },
           {
            url:'/',
            title:'node.js'
          },
        ],
        artList:[
          {
            url:'/',
            title:'如何让你快速的入门vue',
            data:'2018/2/3',
            visited:421
          },
          {
            url:'/',
            title:'如何让你快速的入门vue',
            data:'2018/2/3',
            visited:421
          },
          {
            url:'/',
            title:'如何让你快速的入门vue',
            data:'2018/2/3',
            visited:421
          },
          {
            url:'/',
            title:'如何让你快速的入门vue',
            data:'2018/2/3',
            visited:421
          },
        ]
      }
    },
    mounted (){
      this.getCategory();
    },
    methods: {
      getCategory() {

      }
    },
    components: {
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
    background-color: #fff
  }

  .container {
    height: 699px;
    max-width: 1200px;
    margin: 0 auto;
    background-color: #fff;
  }

  .b-topNav {
    background-color: black;
  }

  .b-bottomLink {
    background-color: rgba(51, 51, 51, 1)
  }

  .siteInfo {
    /* background-color: #000; */
  }

  .mask {
    background-color: rgba(51, 51, 51, 0.2)
  }

  .artContainer {
    display: inline-block;
    width: 79%;
  }

  .rightBanner {
    display: inline-block;
    width: 20%;
    padding-left: 5px;
    text-align: left;
  }

  #searchTxt {
    padding: 3px;
    outline: none;
    border: none;
    border-bottom: 1px solid rgba(51, 51, 51, 0.3);
  }

  #searchTxt:focus {
    outline: none;
    appearance: none;
    border-bottom: 2px solid rgba(34, 34, 34, 1);
  }
  .icon-search{
    font-size: 20px;
    color: #a1a3a5;
    cursor: pointer;
    padding: 2px;
  }
  #searchTxt:focus + .icon-search {
    background: black;
    color: #fff;
    border-radius: 5px;
    padding: 2px;
  }
  .contact, .tags,.newArt{
    line-height: 20px;
    width: 70%;
    margin-top: 20px;
  }
  .contact h1,.tags h1,.newArt h1{
    font-weight: 800;
    font-size: 16px;
  }
  .contact ul{
    margin-top: 16px;
  }
  .contact ul li,.contact ul li a{
    color: rgb(85, 85, 85)
  }
  .contact ul li:hover,.contact ul li a:hover,.art-title:hover{
    color: rgba(253, 159, 45, 1);
    cursor: pointer;
  }
  .contact ul li span{
    float: right;
  }
  .tags li {
    display: inline-block;
    margin:5px 3px 5px 0px;

  }
  .tags-btn{
    color: #000;
    background-color: #fff;
    border: 1px solid #a1a3a5;
    margin: 5px;
    padding: 3px;
    border-radius:3px;
  }
  .tags-btn:hover{
    background-color: rgba(253, 159, 45, 1);
  }
  .artPic{
    display: inline-block;
    width: 32px;
    height: 32px;
  }
  .artPic img{
    height: 100%;
  }
  .introduce{
    display: inline-block;
    padding-left: 3px;
  }
  .introduce li {
    margin: 4px;
  }
  .introduce i{
    vertical-align: middle;
  }
  .art-title{
    width: 120px;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
  }
</style>

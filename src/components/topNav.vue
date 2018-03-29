<template>
  <div>
    <header>
      <div class="topNav">
        <a href="javascript:;" :class="{item:item.className=='item',checked:index==activeIndex}" v-for="(item,index) in navArr" @click='addChose(index,item.path)' :key="item.index">
          <template v-if="item.imgSrc">
                  <img  :class="item.className" :src="item.imgSrc" :alt="item.name">
          </template>
          <template v-else>
            {{item.name}}
          </template>
        </a>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  props:{
    nowIndex:Number
  },
  data() {
    return {
      navArr: [{
            path: '/',
            className: 'item',
            name: '首页'
          },
          {
            path: '/about',
            className: 'item',
            name: '关于'
          },
          {
            path: '/product',
            className: 'item',
            name: '产品'
          },
          {
            path: '',
            className: 'item-img',
            imgSrc: './static/images/taiji.png',
            name: 'blog'
          },
          {
            path: '/blog',
            className: 'item',
            name: '博客'
          },
          {
            path: '/team',
            className: 'item',
            name: '团队'
          },
          {
            path: '/contact',
            className: 'item',
            name: '联系'
          },
        ],
      key: 'value',
      activeIndex:''
    }
  },
  mounted(){
    this.activeIndex = this.$props.nowIndex
  },
  methods: {
    addChose(index,path) {
      this.activeIndex = index;
      this.$router.push({
        path:path
      })
    }
  },
}
</script>

<style scoped>
  .topNav{
    /* background-color: rgba(51, 51, 51, 0.3); */
  }
  .topNav a {
    margin: 20px;
    padding: 0 5px;
    color: #fff;
  }

  .item:hover {
    text-decoration: none;
    border-bottom: 2px solid #fff;
    transition: all;
  }

  .item-img {
    vertical-align: middle;
    animation: spin 4s infinite linear;
  }

  .item-img:hover {
    animation-play-state: paused;
  }

  @keyframes spin {
    0% {
      transform: rotate(360deg);
    }
    100% {
      transform: rotate(0deg);
    }
  }

  .checked {
    text-decoration: none;
    border-bottom: 2px solid #fff;
    transition: all;
  }
</style>

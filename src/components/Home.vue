<template>
  <!-- <div class="home">
    <h1>{{ msg }}</h1>
    <ul>
      <li v-for="article in articles">
      <div class="m-img inl-block">
        <a v-bind:href="article.url">
          <img class="m-img" v-bind:src="article.images.small"/>
        </a>
      </div>
      <div class="m-content inl-block">
            <div> {{article.title}}</div>
            <div>年份：{{article.year}}</div>
            <div>类型：{{article.subtype}}</div>
      </div>
      </li>
    </ul>
  </div> -->
<div class="home">
  <ul class="list-group list-group-lg no-radius m-b-none m-t-n-xxs">
    <li class="list-group-item clearfix b-l-3x b-l-info" v-for="article in articles">
      <a class="avatar thumb pull-left m-r" v-bind:href="article.url">
        <img v-bind:src="article.images.small"/>
      </a>
      <div class="pull-right text-sm text-muted">
        <a class="label bg-danger pull-right m-t-xs" v-bind:href="article.url">查看详情</a>
      </div>
      <div class="clear">
        <div>
          <a v-bind:href="article.url" class="text-md">{{article.title}}</a>
          <span class="label bg-light m-l-sm">tips</span>
        </div>
        <div class="text-ellipsis m-t-xs">年份：{{article.year}}</div>
        <div class="text-ellipsis m-t-xs">类型：{{article.subtype}}</div>
      </div>
    </li>
  </ul>
</div>
</template>


<script>

// mounted 钩子函数  这里去请求数据

export default {
  name: 'home',
  data () {
    return {
      msg: 'list列表',
      articles:[]
    }
  },
  created:function(){  //这里mounted和created生命周期函数区别
     //this.$http.jsonp('https://api.douban.com/v2/movie/top250?count=100', {}, {
     this.$http.get('../static/mock/data.json', {}, {
        headers: {

        },
        emulateJSON: true
    }).then(function(response) {
      // 这里是处理正确的回调
        console.log(response);
        this.articles = response.data.subjects
        // this.articles = response.data["subjects"] 也可以

    }, function(response) {
        // 这里是处理错误的回调
        console.log(response)
    });
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul{
  list-style: none;
  margin: 0;
  padding: 0;
}
ul li{
border-bottom: 1px solid #999;
padding: 10px 0;
}

.inl-block{
display: inline-block;
}

.m-img{
  width: 100px;
  height: 100px;
}
.m-content{
margin-left: 20px;
}
.bg-light{
  color: #58666e
}
.label.bg-danger.pull-right.m-t-xs{
  background-color: #428bca;
  padding: 6px 10px;
}
</style>

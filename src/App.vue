<template>
  <div id="app">
    <!-- <nav class="navbar navbar-inverse">
      <div class="container-fluid">
        <div class="navbar-header">
          <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-2">
            <span class="sr-only">Toggle navigation</span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
          </button>
          <a class="navbar-brand" href="/home">Brand</a>
        </div>

        <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-2">
          <ul class="nav navbar-nav">
            <li class="active"><router-link to="/home">Home</router-link></li>
            <li><router-link to="/about">About</router-link></li>
          </ul>
          <ul class="nav navbar-nav navbar-right">
            <li><router-link to="/User">User</router-link></li>
          </ul>
        </div>
      </div>
    </nav> -->
    <div class="nav-tabs-alt">
        <ul class="nav nav-tabs nav-justified">
          <li class="active"><router-link to="/home">Home</router-link></li>
          <li><router-link to="/about">About</router-link></li>
          <li><router-link to="/User">User</router-link></li>
        </ul>
      </div>
    <div class="nav">
        <!-- 使用 router-link 组件来导航. -->
        <!-- 通过传入 `to` 属性指定链接. -->
        <!-- <router-link> 默认会被渲染成一个 `<a>` 标签 -->
        <!-- <ul>
          <li><router-link to="/home">Home</router-link></li>
          <li><router-link to="/about">About</router-link></li>
          <li><router-link to="/User">User</router-link></li>
        </ul> -->
    </div>
     <div class="main">
     <!-- 路由匹配到的组件将渲染在这里 -->
       <router-view></router-view>
     </div>
  </div>
</template>

<script>
// import Hello from './components/Hello'

export default {
  name: 'app',
  components: {
    // Hello
  }
}
</script>

<style>
  .navbar,.container-fluid{
    border-radius: 0;
    background: #23b7e5;
    border:1px solid #23b7e5;
  }
  .container-fluid a{
    color: #fff
  }
</style>

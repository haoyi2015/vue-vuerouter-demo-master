<template>
  <div class="user">
    <h1>{{ msg }}</h1>
    使用user以下技术栈：<br/>
    关于user
  </div>
</template>

<script>
export default {
  name: 'user',
  data () {
    return {
      msg: 'user',
      userDataList:[]
    }
  }
}
</script>
<style scoped>

</style>

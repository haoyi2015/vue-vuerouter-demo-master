<template>
  <div class="detail">
    <h1>{{ msg }}</h1>
    <ul class="detail-box">
      <li v-for="detail in detailData">
          <span v-bind:data-code="detail.code" v-on:click="code(this,detail.code)">code</span>
          <span>{{detail.name}}</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'detail',
  data () {
    return {
      msg: 'detail',
      detailData:[]
    }
  },
  created:function(){  //这里mounted和created生命周期函数区别
     this.$http.get('http://192.168.252.1:8006/src/mock/detail.json', {}, {
        headers: {

        },
        emulateJSON: true
    }).then(function(response) {
      // 这里是处理正确的回调
        this.detailData = response.data
        // this.articles = response.data["subjects"] 也可以

    }, function(response) {
        // 这里是处理错误的回调
        console.log(response)
    });
  },
  methods:{
    code: function(e,c){

      //过滤当前元素
      var item =this.detailData,
          _code =c,
          arr =[];

      for (let value of item) {
        if(value.code!=c){
          arr.push({
            code:value.code,
            name:value.name
          })
        }
      }
      this.detailData =arr;
    }
  }
}
</script>

<style scoped>
  .detail-box{

  }
</style>

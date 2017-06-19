<template>
  <div >
    <div style="position: absolute;width:100%; height:100%; z-index: -1;background-color: #42b983">
      <img src="/static/image/0_0启动页面.jpg" height="100%" width="100%" >
    </div>
     <div style="position: absolute;width:100%; height:100%">
       <mt-button style="top: 60%" @click="handleClick">按钮</mt-button>
      </div>
    </div>
  </div>
</template>
<script>
import { Toast } from 'mint-ui'
import axios from 'axios'
// var aa = {}
var instance = axios.create({
  baseURL: 'http://127.0.0.1:10010/',
  timeout: 1000
})
export default {
  data () {
    return {
    }
  },
  mounted: function () {
    instance.get('/hello?name=Scott')
    .then(function (response) {
      console.log(response)
    })
  .catch(function (error) {
    console.log(error)
  })
  },
  methods: {
    handleClick: function () {
      Toast('提示信息')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

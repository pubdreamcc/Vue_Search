<template>
  <div id="app">
    <img src="./assets/logo.png">
    <input type="text" v-model="msg">
    <ul id='list'>
      <li v-for="(item,index) in show(msg)" :key="index"><span>品牌：{{item.name}}</span><span>价格:{{item.price}}</span></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      list: [
        {name: '奔驰', price: 28},
        {name: '宝马', price: 30},
        {name: '大众', price: 60}
      ],
      msg: ''
    }
  },
  methods: {
    show (keywords) {
      let newList = []
      this.list.forEach((item) => {
        if (item.name.indexOf(keywords) !== -1) {
          newList.push(item)
        }
      })
      return newList
    }
  }
}
</script>

<style>
  #app{
    position: relative;
    text-align: center;
  }
  #list,li{
    margin: 0;
    padding: 0;
  }
  #list{
    position: absolute;
    left: 50%;
    transform: translateX(-50%); width: 173px;
    list-style: none;
  }
  #list li{
    background: gray;
    color: #bbffaa
  }
  #list li:hover{
    background: rebeccapurple;
    color: tomato;
    opacity: 1;
  }
</style>

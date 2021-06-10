<template>
  <banner/>

  <div class="black-bg" v-if="proView==true">
    <div class="white-bg">
      <img v-bind:src="product[0].image">
      <div>{{product[0].title}}</div>
      <div>{{product[0].price}}</div>
      <div>{{product[0].content}}</div>
      <button v-on:click="proView=false">닫기</button>
    </div>
  </div>


  <ul class="view">
    <li v-for="(item,i) in product" :key="i">
      <img v-bind:src="product[i].image">
      <div>{{product[i].title}} <span v-on:click="proView=true">[상세보기]</span></div>
      <div>{{product[i].price}}</div>
    </li>
  </ul>
  

</template>

<script>
import vdata from './data.js'
import banner from './components/banner.vue'



export default {
  name: 'App',
  data(){
    return{
      proView:false,
      product:vdata,
    }
  },
  components:{
    banner
  }
 
}
</script>

<style>
  html,body{height: 100%;}
  *{margin: 0;padding: 0;}
  li{list-style: none;}
  img{width: 100%;}
  .view li{margin-bottom:20px;}
  .black-bg{
    position: fixed;width: 100%;height:100%;background:rgba(0,0,0,0.5);
    top:0;display: flex;justify-content: center;align-items: center;
    }
  .white-bg{
    width: 80%;background:#fff;border-radius: 5px;
    padding:20px

  }
</style>

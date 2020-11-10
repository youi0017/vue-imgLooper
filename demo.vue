<template>
    <h1 class="text-center">
      Vue轮播图组件使用示例
    </h1>
    
	<imglooper height="250px" interval="2000"></imglooper>
</template>

<script>
import imglooper  from "../../components/Lunbo.vue";

export default {
  data () {
    return {
      msg: 'chy 2020-11'
    }
  },
  components:{
	 imglooper
  }
  
}
</script>

<style>

</style>

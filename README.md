# vue-imgLooper
最简单的 轮播图组件


```
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
      msg: 'hellow imgLooper!'
    }
  },
  components:{
	 imglooper
  }
  
}
</script>

<style>

</style>

```



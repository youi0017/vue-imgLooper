<style scoped>
	.lunboBox{
		position: relative;
		overflow: hidden;
	}
	
	.imgLunboBox{
		height: 100%;
	}
	
	img{
		display: block;
		width: 100%;
		height: 100%;
		/* transition: hidden 2s; */
	}
	
	.ctlLunboBox{
		position: absolute;
		bottom: 1rem;
		width: 100%;
		display: flex;
		justify-content: center;
	}
	
	.ctlLunboBox li{
		width: 2rem;
		height: .8rem;
		background-color: #AAA;
		border: 1px solid #FFF;
		margin:0 .5rem;
		cursor: pointer;
	}
	
	.ctlLunboBox li:hover, .ctlLunboBox li.active{
		background-color: #000;
	}
	
	
</style>

<template>
<div class="lunboBox" :style="{height: height}">
	<div class="imgLunboBox">
			<img v-for="(img, i) in imgs" v-show="i===this.idx" :src="img.src" />
	</div>
	<ul class="ctlLunboBox">
		<li :class="{active: idx==this.idx}" @mouseout="run()" @mouseover="stop(idx)" v-for="(img, idx) in imgs">
		</li>
	</ul>
</div>
</template>

<script>
import img1 from "../assets/img/1.jpg";
import img2 from "../assets/img/2.jpg";
import img3 from "../assets/img/3.jpg";

export default {
  name: 'imgLooper',
  props: {
	  height: {
	    type: String,
	    default: "250px"
	  },
	  interval:{
		  type:Number,
		  default: 3000
		  
	  }
    // _imgs
  },
  methods:{
	stop(idx){
		// 停止混动
		this.timer=clearInterval(this.timer);
		// 选择当前
		this.chg(idx);

	},
	chg(idx){
		this.idx = idx;
	},
	run(){
		// console.log(this.interval);
		this.timer = setInterval(()=>{			
			let idx = this.idx>=(this.imgs.length-1) ? 0 : (this.idx+1)
			this.chg(idx);
		}, this.interval);
	}
  },
  mounted() {
	  // 启动轮播
	  this.run();
  },
  data() {
    return {
		timer:null,
		idx:0,
	  imgs:[
		  {
			src: img1,
			href:"",
			target:"", 
		  },
		  {
			src: img2,
			href:"",
			target:"", 
		  },
		  {
			src: img3,
			href:"",
			target:"", 
		  }, 
	  ]
    }
  }
}
</script>

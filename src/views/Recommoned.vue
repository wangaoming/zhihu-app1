<template>
  	<div class="box1">
		<h3>推荐</h3>
		</div>
</template>

<script>
// http://v.juhe.cn/toutiao/index?type=&key=aeed60af1d88866d68868bb5c973a77b
export default {
  name: 'recommoned',
  data() {
  		return {};
  	},
  	created(){
  	      axios.get('http://v.juhe.cn/toutiao/index?type=&key=aeed60af1d88866d68868bb5c973a77b')
  	       //then获取成功；response成功后的返回值（对象）
  	      .then(response=>{
  	         console.log(response);
  	         this.oftenGoods=response.data;
  	      })
  	       //获取失败
  	      .catch(error=>{
  	        console.log(error);
  	        alert('网络错误，不能访问');
  	      })
  	}
  };
</script>


<style l ang="scss" scoped>
	.box1{
		margin-left: 150px;
		margin-top: -20px;
		height:350px;
		width: 700px;
		background-color: white;
	}
	h3{
		font-size: 30px;
	}
</style>
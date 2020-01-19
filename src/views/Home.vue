<template>
	<div class="home">
		
	
  	<div class="home-bar">
		<ul class="home-list">
			<li class="home-item">
				<router-link class="router" to="/home/recommoned">推荐</router-link>
			</li>
			<li class="home-item">
				<router-link class="router" to="/home/follow">关注</router-link>
			</li>
			<li class="home-item">
				<router-link class="router" to="/home/hot">热榜</router-link>
			</li>
		</ul>
		
		
  	</div>
	<!-- 二级路由进口 -->
	<router-view class="container"/>
	</div>
</template>

<script>
export default {
  name: 'home',
  data() {
  		return {};
  	},
  	created() {}
  };
</script>


<style lang="scss" scoped>
	
	.home{
	
		position: relative;
		margin-bottom:-20px;
	}
	.home-bar{
		margin-left: 150px;
		width: 700px;
		height: 70px;
		background-color: white;
	}
	
	.router{
		color: black;
		text-decoration: none;
	}
	// 点击文字后的颜色
	.router-link-active {
		color: skyblue;
	}
	
	.home-list{
		height: 70px;
		list-style: none;
	}
	
	.home-item{
		list-style: none;
		float: left;
		width: 100px;
		font-size: 20px;
		text-align: center;
		line-height: 80px;
		box-sizing: border-box;
	}
	
</style>
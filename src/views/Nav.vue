<template>
	<div>
		<div class="nav gutter">
			<div class="nav-bar">
				<!-- <img class="img" src="../assets/image/font.png" /> -->
				<ul class="nav-list flex-left">
					
					<li class="nav-img"><img class="img" src="../assets/image/font.png" /></li>
					<li class="nav-item">
						<router-link class="router" to="/home">首页</router-link>
					</li>
					<li class="nav-item">
						<router-link class="router" to="/explore1">发现</router-link>
					</li>
					<li class="nav-item">
						<router-link class="router" to="/question/waiting">等你来答</router-link>
					</li>
					<li class="nav-item abs-center-right">
						<router-link class="router" to="/login">登录</router-link>
					</li>
				</ul>
			</div>
			<div class="div1"></div>
		</div>
		
		 <router-view class="container"/>
	</div>
	<!-- 二级路由入口 -->
	
</template>

<script>
	export default {
		name: 'nav',
		data() {
			return {};
		},
		created() {}
	};
</script>

<style lang="scss" scoped>

    .img{
	    margin-top:25px;
		height:35px;
	}
	.router{
		width: 150px;
		color: skyblue;
		text-decoration: none;
	}
	
	.router-link-active {
		color: blue;
	}
	
	.nav-bar{
		height: 80px;
		background-color: white;
	}
	.gutter {
		position: relative;
		margin-bottom: 10px;
	}
	.nav-list{
		height: 80px;
		width: 100%;
		background-color: white;
		list-style: none;
	}
	
	.nav-item{
		list-style: none;
		float: left;
		width: 100px;
		background-color:white;
		font-size: 20px;
		text-align: center;
		line-height: 80px;
		box-sizing: border-box;
	}
.nav-img{
	list-style: none;
	float: left;
	width: 100px;
	background-color:white;
	text-align: center;
	box-sizing: border-box;
}

	li:nth-child(1){
			margin-left: 50px;
	}
	li:nth-child(5){
			margin-left: 600px;
	}
</style>
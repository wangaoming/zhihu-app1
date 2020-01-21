<template>
	<div>
		
		<!-- 专题 -->
		
		<div class="container">
			<div class="row">
				<div class="banner">
					<i class="iconfont"><img src="../assets/image/copy.png"/></i>
					<h2>最新专题</h2>
				</div>
				<div class="row1">
				<div class="card" v-for="(item,index) in specials" :key="index">
					<!-- 正题部分 -->
						<img :src="item.banner" alt="" class="card-head">
						<div class="b1">
						<div class="card-body flex">
							<div class="left">
								<div class="left1">
							<h3>{{item.title}}</h3>
							</div>
							<p class="meta">{{item.updated}}更新,{{item.viewCount}}浏览</p>
							</div>
							<div class="right">
								<button class="btn_gz">关注专题</button>
							</div>
							
						</div>
						</div>
						<p class="introduction">{{item.introduction}}</p>
						<div class="card-buttom">
						<span v-for="(section,index) in item.sections" :key="index" class="section flex">
							{{section.sectionTitle}}
						</span>
						</div>
					</div> 
					
					</div>
					<button class="center"><router-link to="/special/all" class="l">查看更多专题 ></router-link></button>
			</div>
			
			<!-- 圆桌 -->
			
			
			<div class="row">
				<div class="banner">
					<i class="iconfont"><img src="../assets/image/copy.png"/></i>
					<h2>圆桌讨论</h2>
				</div>
				<div class="row1">
				<div class="card" v-for="(item,index) in roundTables" :key="index">
						<div class="cards-head">
							<!-- <div class="card-background"> -->
								<img :src="item.banner" alt="" class="card-background">
							
							<div class="card-main">
								<p class="name">{{item.name}}</p>
								<p>{{item.visitsCount}}人访问,{{item.includeCount}}人参与</p>
							</div>
							<div class="card-btn">
								<button class="btn_gz">关注圆桌</button>
							</div>
							</div>
						<!-- <div class="card-body flex"> -->
							<a class="introduction">
							{{item.urlToken}}
						
							</a>
							<a class="meta1">
							{{item.visitsCount}}点击</a>
							<a class="introduction">
						啦啦啦啦啦
							</a>
							<a class="meta1">
							730 个回答</a>
							<a class="introduction">
						啦啦啦啦啦
							</a>
							<a class="meta1">
							120 个回答</a>
						<!-- </div> -->
						<div class="card-buttom">
						<span v-for="(section,index) in item.sections" :key="index" class="section flex">
							{{section.sectionTitle}}
						</span>
						</div>
					</div> 
					
					</div>
					<button class="center"><router-link to="/roundTable/all" class="l">查看更多圆桌></router-link></button>
			</div>
			
			<!-- 收藏 -->
			<div class="row">
				<!-- 热门收藏夹标题 -->
				<div class="banner">
					<i class="inconfont"><img style="height: 40px;width: 40px;" src="../assets/image/copy.png"/></i>
					<h2>热门收藏夹</h2>
				</div>
				<div class="row1">
					<div class="card"  v-for="(item,index) in favourites" :key="index" >
						<!-- 正题部分 -->
					<div>
						<h2 style="margin-left: 20px;">{{item.title}}</h2>
						<button class="btn_gz" style="margin-top: -50px;">关注收藏夹</button>
						<div style="text-align: -moz-center;margin-left: 20px;">
						<p style="color: #d6d6d6;font-size: 10px;text-align: top;"><img :src="item.creatorAvatar" /><strong style="color: #000000;font-size: 15px;">{{item.creatorName}}</strong> 创建 | {{item.followers}}人关注</p>
						 </div>
						 <hr  class="hr1"/>
					</div>
					<div style="margin-left: 20px;">
						<strong style="color: #000000;font-size: 15px;">{{item.questionTitle}}</strong>
						<p style="font-size: 15px;">{{item.answerAuthorName}}:{{item.answerContent}}</p>
						<p style="color: #d6d6d6;font-size: 10px;text-align: top;">回答 {{item.voteUpCount}}赞同.{{item.commentCount}}评论</p>
					</div>
					<div style="margin-left: 20px;">
						<strong style="color: #000000;font-size: 15px;">{{item.questionTitle}}</strong>
						<p style="font-size: 15px;">{{item.answerAuthorName}}:{{item.answerContent}}</p>
						<p style="color: #d6d6d6;font-size: 10px;text-align: top;">回答 {{item.voteUpCount}}赞同.{{item.commentCount}}评论</p>
					</div>
					<div style="margin-left: 20px;">
						
					</div>
					<strong style="color: #175199;font-size: 15px;margin-left: 20px;" >已收藏{{item.totalCount}}条内容</strong>
					</div>
				
			</div>
			</div>
			<button class="center" style=""><router-link to="/Favorite/all" class="l">查看更多收藏夹></router-link></button>
			
		</div>
	</div>
</template>

<script>
export default{
	name:'special',
	data(){
		return{
			specials:[],
			roundTables:[],
			favourites:[],
		};
	},
	created() {
		// 最新专题
		this.axios.get('http://localhost:8080/api/special').then(res =>{
			console.log(res);
			this.specials = res.data.data;
		});
		// 圆桌
		this.axios.get('http://localhost:8080/api/roundTable').then(res =>{
			console.log(res);
			this.roundTables = res.data.data;
		});
		// 收藏夹
		this.axios.get('http://localhost:8080/api/favorite').then(res =>{
			console.log(res);
			this.favourites = res.data.data;
		});
	}
};
</script>

<style  lang="scss" scoped>
	.center{
		margin-right: 400px;
	}
	.banner{
		width: 100%;
		margin-bottom: 10px;
		margin-top: 10px;
		height: 60px;
		display: flex;
		align-items: center;
		font-size: 20px;
		margin-left: 150px;
	}
	.iconfont{
		color: rgb(0,132,255);
		font-size: 32px;
		margin-right:10px;
	}
	.row1{
	margin-left: 80px;
	margin-right: 150px;
	// padding-top: 20px;
	// 弹性布局
	display: flex;
	flex-wrap: wrap ;
	 // align-content: flex-start;
	}
	.left{
		width: 60%;
		
	}
	.b1{
		 position: relative;
		border-radius: 4px;
		-webkit-box-shadow: 0 1px 3px 0 rgba(0,0,0,.1);
		box-shadow: 0 1px 3px 0 rgba(0,0,0,.1);
		overflow: hidden;
	}
	.left1{
		cursor: pointer;
	}
	.right{
		width: 40%;
		margin-left: 45px;
		margin-bottom: 30px;
		margin-top: 30px;
	}
	.card{
		background-color: rgb(255,255,255);
		border: 2px solid #d6d6d6;
		box-shadow: 0 1px 3px 0 rgba(26,26,26,.1);
		border-radius: 5px;
		width: 600px;
		height: 470px;
		margin-bottom: 30px;
			margin: 0vh auto 0;
			margin-top: 20px;
		box-shadow: 2px 5px 5px #aaa;
		margin-left: 50px;

		
	}	
	.card-head{
		width: 100%;
	}
	.cards-head{
		
		position: relative;
		height: 240px;
		background-image: linear-gradient(to right, rgb(255, 215, 44) 0%, rgba(255, 215, 44, 10) 100%);
		
	}
	.card-background{
		float: right;
		width: 200px;
		height: 100%;
		
	}
	.card-main{
		position: relative;
		width: 320px;
		padding: 68px 24px 24px;
	}
	.card-btn{
		position: absolute;
		right: 24px;
		bottom: 24px;
		background-color: white;
		border-radius: 5px;
	}
	.card-body{
	display: flex;
	align-items: center;
	justify-content: space-between;
	padding-left: 20px;
	}
	.btn_gz{
		-webkit-tap-highli0ht-color: rgba(26,26,26,0);
		font: inherit;
		cursor: pointer;
		background: none;
		border: none;
		outline: none;
		-webkit-appearance: none;
		height: 34px;
		border-radius: 3px;
		font-size: 14px;
		font-weight: 600;
		width: 102px;
		color: #0084ff;
		background-color: rgba(0,132,255,.08);
		float: right;
		text-align: center;
		margin-right: 20px;
		
		
	}
	.introduction{
		display: flex;
		margin-top: 15px;
		margin-left: 15px;
		cursor: pointer;
	}
	.meta1{
		color: #d6d6d6;
		font-size: 10px;
		text-align: top;
		margin-left: 15px;
	}
	.name{
		font-size: 28px;
		font-weight: 660;
		color: white;
		margin-bottom: 30px;
			cursor: pointer;
	}
	.col-6{
		flex: 0 0 50%;
		img{
			width: 100%;
			height: 100%;
			padding: 5px;
			cursor: pointer;
		}
	}
	.meta{
		color: #d6d6d6;
		font-size: 10px;
		text-align: top;
	}
	.center{
		    -webkit-box-align: center;
    align-items: center;
    padding: 0 14px 0 24px;
    height: 48px;
	width: 250px;
    background-color: #fff;
    border-radius: 25px;
    color: #8590a6;
    cursor: pointer;
    font-weight: 600;
	margin-left: 810px;
	margin-right: 670px;
	margin-top: 30px;
	text-align: center;
	font-size: 20px;
	
	
	}
	.hr1{
		width:570px; height:1px;border:none;border-top:1px solid #aeaeae ;padding-left:5px;
		margin-top: 20px;
		margin-bottom: 10px;
	}
</style>
<template>
	<div>
		<div class="container">
			<div class="row">
				<hr />
				<div class="banner">
					<i class="iconfont"><img style="height: 40px;width: 40px;" src="../assets/image/copy.png"/></i>
					<h3>热门收藏夹</h3>
				</div>
				<div class="col-12 box" v-for="(item,index)  in  favourites" v-if="index>begin&&index<end" :key="index">
						<div class="box-left" style="margin-left: 20px;"><h2 style="margin-left: 20px;">{{item.title}}</h2>
							<div style="text-align: -moz-center;margin-left: 20px;">
						   <p style="color: #d6d6d6;font-size: 10px;text-align: top;"><img :src="item.creatorAvatar"  style="width: 40px;height: 40px;"/><strong style="color: #000000;font-size: 15px;">{{item.creatorName}}</strong> 创建</p>
						   </div>
						  
							   <button class="btn_gz" style="margin-right: 420px;">关注收藏夹</button>
							   <p style="color: #d6d6d6;font-size: 15px;text-align: top;margin-left: 140px;"> {{item.followers}}人关注</p>
						</div>
						<div class="vLine"></div>
						<div style="margin-left: 20px;margin-top: 10px;">
							<strong style="color: #000000;font-size: 15px;">{{item.questionTitle}}</strong>
							<p style="font-size: 15px;">{{item.answerAuthorName}}:{{item.answerContent}}</p>
							<p style="color: #d6d6d6;font-size: 10px;text-align: top;">回答 {{item.voteUpCount}}赞同.{{item.commentCount}}评论</p>
							<strong style="color:#175199;font-size: 15px;" >已收藏{{item.totalCount}}条内容></strong>
						</div>
						
						</div>
					</div> 
			</div>
			<button @click="show_all" class="flex center btn_gz">展开全部>>></button>
		</div>
		
	</div>
</template>

<script>
export default{
	name:'favorite',
	data(){
		return{
		favourites:[],
			begin:0,
			end:6,
		};
	},
	created() {
		this.axios.get('http://localhost:8080/api/favorite/all').then(res =>{
			console.log(res);
			this.favourites= res.data.data;
		});
	},
	methods: {
	show_all(){
	this.begin=0;
	this.end =this.favourites.length;
	}						
	},					
};
</script>

<style  lang="scss" scoped>
	.banner{
		width: 100%;
		margin-bottom: 10px;
		margin-top: -10px;
		height: 60px;
		display: flex;
		background: white;
		align-items: center;
		font-size: 20px;
	}
	.iconfont{
		color: rgb(0,132,255);
		font-size: 32px;
		margin-right:10px;
	}
	.box{
		display: flex;
		width: 100%;
		height: 180px;
		margin-bottom: 20px;
		padding: 25px;
		background-color: white;
	}
	.box-left{
		width: 35%;
		margin-right: 20px;
		img{
			width: 100%;
			height: 100%;
		}
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
		
		
		
	}
	.box-right{
		width: 65%;
		position: relative;
	}
	.box-head{
		display: flex;
	}
	.left{
		width: 83%;
	}
	.right{
		width: 17%;
		margin-bottom: 30px;
	}
	.box-bottom{
		display: flex;
		position: absolute;
		left: 0;
		bottom: 0;
	}
	.section{
		padding: 0 8px;
		height: 24px;
		line-height: 24px;
		border-radius: 5px;
		background-color: #f6f6f6;
		color: #8590a6;
		font-size: 12px;	
	}
	
	.introduction{
		display: flex;
	}
	
.vLine {
    border-left: solid 2px #ccc;
    height: 170px;
    vertical-align: middle;
    display: inline-block;
    
	
}
</style>
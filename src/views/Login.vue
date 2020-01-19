<template>
	<div class="login-bar tx-center">
		<router-link to="/">
			<div style="text-align: center">
			<img src="https://pic4.zhimg.com/80/v2-a47051e92cf74930bedd7469978e6c08_hd.png" class="logo" /></div>
		</router-link>
		
		<div>
			<form>
				<div class="SignContainer-inner">
				<div class="login-bar1">
				<ul class="login-list">
					<li class="login-item">
						<router-link class="router" to="/home/recommoned">免密码登录</router-link>
						</li>
					<li class="login-item">
						<router-link class="router" to="/home/follow">密码登录</router-link>
						</li>
						
					<div class="SignFlow-qrcodeTab">
						
						</div>
						</ul>
						</div>
						</div>
			</form>
	</div>
	<div class="tel">
					<div class="num"><select>
						<option>中国 +86</option>
						<option>美国 +1</option>
						<option>英国 +44</option>
						<option>新加坡 +65</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
						<option>其他...</option>
					</select></div>
					<div class="telnum"><input type="text" placeholder="手机号" /></div>
				</div>
				
				<div class="mess">
				<div class="message"><input type="text" placeholder="请输入6位短信验证码"/></div>
				<div class="getmess"><a href="#">获取短信验证码</a></div>
				</div>
				
				<div class="voice"><a href="#">接收语音验证码</a></div>
				<button class="register">注册</button>
				<div class="zhuce">
					<div class="xieyi">注册即代表你同意 <a href="#">《知乎协议》</a></div>
					<div class="jigouhao"><a href="#">注册机构号</a></div>
				</div>
				<div class="login"><div class="logina">已有帐号?<a href="#">登录</a></div></div>
			</div>
			
			
		


	
</template>

<script>
	
export default{
	name: 'login',
	data(){
		return {};
	},
	created(){}
};
</script>

<style lang="scss" scoped>
	.login-bar{
		background-image: url(https://static.zhihu.com/heifetz/assets/sign_bg.db29b0fb.png);
		background-repeat: no-repeat;
		background-color: #b8e5f8;
		background-size: cover;
		width: 100%;
		height: 100vh;
		overflow: auto;
		
		.logo{
			width: 128px;
			height: 81px;
			margin-bottom: 24px;
			margin-top: 100px;
		}
		form{
			width: 400px;
			height: 320px;
			background-color: white;
			margin: 0vh auto 0;
			
		}
		.SignContainer-inner {
    position: relative;
    border-radius: 4px;
    -webkit-box-shadow: 0 1px 3px 0 rgba(0,0,0,.1);
    box-shadow: 0 1px 3px 0 rgba(0,0,0,.1);
    overflow: hidden;
}
		.login-bar1{
			width:400px;
			height: 40px;
			background-color: white;
		}
		.router{
				width: 150px;
			color: black;
			text-decoration: none;
		}
		
		.router-link-active {
			border-bottom: 2px solid #000;
			
		}
		
		.login-list{
			height: 80px;
			width: 100%;
			text-color: blue;
			list-style: none;
		}
		.login-item{
			list-style: none;
			float: left;
			width: 100px;
			font-size: 15px;
			text-align: left;
			line-height: 20px;
			box-sizing: border-box;
		}
		.main{
				margin:55px auto 30px auto;
				height:500px;
				width: 430px;
				border: 1px solid white;
				background-color: white;
			}
			.SignHeader{
				margin:30px auto 0 auto;
				color:#0084FF;
				font-family: "黑体";
				font-size: 23px;
			}
			.Signslogen{
				margin:18px auto 38px auto;
			}
			.download{
				background-color:#8590A6;
				color:white;
				font-family:"黑体";
				font-size:15px;
				margin: auto;
				width:430px;
				height:40px;
				cursor:pointer;
				border-radius: 5px;
			}
			.tel{
				
			}
			.num{
				margin:auto 0 auto 33px;
				float:left;
				height:45px;
				width:110px;
			}
			.telnum{
				float:right;
				height:45px;
				width:245px;
				text-align: left;
			}
			.mess{
				width:450px;
				height:60px;
			}
			.message{
				margin: auto 43px;
				border:0 solid #EBEBEB;
				border-bottom:1px solid #EBEBEB;
				float:left;
			}
			.getmess{
				margin: auto 65px auto auto;
				border:0 solid #EBEBEB;
				border-bottom:1px solid #EBEBEB;
				float:right;
				font-size:14px;
				/*color:#175199;*/
			}
			.voice{
				float:right;
				margin:30px 45px 30px auto;
				font-size:14px;
			}
			.register{
				width:350px;
				height:40px;
				font-size: 15px;
				background-color:#0077E6;
				color:white;
				cursor: pointer;
				border-radius: 5px;
			}
			.zhuce{
				margin: 30px auto 80px 45px;
				font-size:14px;
			}
			.xieyi{
				float:left;
				color:#8590A6;
			}
			.jigouhao{
				float:right;
				margin:auto 40px auto auto;
				color:#175199;
			}
			.getmess a:link,.getmess a:visited,.getmess a:active,.getmess a:hover,
			.login a:link,.login a:visited,.login a:active,.login a:hover,
			.jigouhao a:link,.jigouhao a:visited,.jigouhao a:active,.jigouhao a:hover{
				text-decoration: none;
				color: #175199;
				}
			.voice a:link,.voice a:visited,.voice a:active,.voice a:hover,
			.xieyi a:link,.xieyi a:visited,.xieyi a:active,.xieyi a:hover{
				text-decoration: none;
				color: #8590A6;
			}
			.login{
				height:56px;
				background-color:#F6F6F6;
				border:1px solid #ebebeb;
			}
			.logina{
				font-family:"黑体";
				font-size:16px;
				margin:20px auto auto auto;
			}
			
}

		
</style>

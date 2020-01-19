<template>
	<div>
		<div class="banner">
			<img src="../assets/image/樱桃.png" alt="" />
			<h3>全部专题</h3>
		</div>
		<div class="container">
			<div class="row" v-for="(item, index) in specials" :key="index">
				<div class="col-4"><img :src="item.banner" alt="" /></div>
				<div class="col-8">
					<h3>{{ item.title }}</h3>
					<p class="meta">{{ item.updated }}更新, {{ item.viewCount }}次浏览</p>
					<p class="introduction">{{ item.introduction }}</p>
					<span v-for="(section, index) in item.sections" :key="index" class="section">
						{{ section.sectionTitle }}
					</span>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'special',
		data() {
			return {
				specials: []
			};
		},
		created() {
			this.axios.get('https://localhost:8080/api/special/all').then(res => {
				console.log(res);
				this.specials = res.data.data;
			});
		}
	};
</script>

<style lang="scss" scoped>
	.banner{
		width: 100%;
		margin-bottom: 10px;
		margin-top: -10px;
		height: 60px;
		border: 1px solid #d6d6d6;
		box-shadow: 2px 5px 5px #ddd;
		padding-left: 10%;
		display: flex;
		align-items: center;
		img{
			height: 60%;
		}
	}
	
</style>
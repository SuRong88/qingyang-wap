<template>
	<div class="hotel-reservation reservation">
		<div class="header">
			<img class="icon-back" src="../assets/images/Return.png" alt="" />
			<p class="h-title">
				{{$route.meta.title}}
			</p>
			<img @click="isSpread = !isSpread" class="icon-more" src="../assets/images/header_more.png" alt="" />
			<ul class="nav" :class="{ spread: isSpread }">
				<router-link to="/index" tag="li" class="nav-item flex flex-ver">
					<img class="icon" src="../assets/images/more_home.png" alt="" />
					<span>首页</span>
				</router-link>
				<router-link to="/me/index" tag="li" class="nav-item flex flex-ver">
					<img class="icon" src="../assets/images/more_me.png" alt="" />
					<span>个人中心</span>
				</router-link>
			</ul>
		</div>
		<div class="main-box">
			<div class="reservation-top">
				<h2 class="m-title">
					长隆横琴湾酒店(珠海海洋王国店)
				</h2>
				<h3 class="m-subtitle">
					商务大床房
				</h3>
				<div class="date-box flex flex-jcsb flex-ver">
					<p>
						入住
						<span class="date">10月31日</span>
						<span class="time">1晚</span>
						离店
						<span class="date">10月31日</span>
					</p>
					<span class="btn-r btn-edit">修改</span>
				</div>
				<div class="about-box flex flex-jcsb flex-ver">
					<p class="flex flex-ver">
						大床1.8米
						<span class="spe"></span>
						30㎡
					</p>
					<span class="btn-r btn-edit">修改</span>
				</div>
				<div class="order-now-box flex flex-jcsb flex-ver">
					<span class="order-num">
						预订数量
					</span>
					<p class="flex">
						<span class="reduce-btn"></span>
						<span class="num-btn">2</span>
						<span class="add-btn"></span>
					</p>
				</div>
			</div>
			<div class="form-box form-box1">
				<h3 class="form-title">
					联系人信息
				</h3>
				<ul>
					<li class="form-item flex">
						<label for="">联系人</label>
						<input class="item-input" type="text" >
					</li>
					<li class="form-item flex">
						<label for="">手机号码</label>
						<input class="item-input" type="text" >
					</li>
					<li class="form-item flex">
						<label for="">电子邮箱</label>
						<input class="item-input" type="text" >
					</li>
					<li class="form-item flex">
						<label for="">订单备注</label>
						<input class="item-input" type="text" >
					</li>
				</ul>
			</div>
			<div class="form-box form-box2">
				<h3 class="form-title">
					旅客信息
				</h3>
				<ul>
					<li class="form-item">
						<label for=""></label>
						<input class="item-input" type="text" >
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
import vHeader from 'components/common/Header.vue';
export default {
	components:{
		vHeader
	},
	created() {},
	mounted() {},
	data() {
		return {
			// 头部 菜单展开
			isSpread: false,
			touristLists:[
				{
					gender:''
				}
			]
		};
	},
	computed: {},
	watch: {},
	methods: {}
};
</script>

<style></style>

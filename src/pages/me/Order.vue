<template>
	<div class="me-order">
			<div class="fix">
				<div class="type-menu-box">
					<!-- 两侧 -->
					<img class="icon-back" src="../../assets/images/header_Return.png" alt="" />
					<img @click="isSpread1 = !isSpread1" class="icon-more" src="../../assets/images/header_more.png" alt="" />
					<ul class="nav" :class="{ spread: isSpread1 }">
						<router-link to="/index" tag="li" class="nav-item flex flex-ver">
							<img class="nav-icon" src="../../assets/images/more_home.png" alt="" />
							<span>首页</span>
						</router-link>
						<router-link to="/me/index" tag="li" class="nav-item flex flex-ver">
							<img class="nav-icon" src="../../assets/images/more_me.png" alt="" />
							<span>个人中心</span>
						</router-link>
					</ul>
					<!-- 中部 -->
					<div class="current-type" @click="isSpread2 = !isSpread2">
						{{currentTypeText}}
						<img class="icon" :class="{'rotate180':isSpread2}" src="../../assets/images/down_arrow2.png" alt="">
					</div>
					<ul class="type-menu" :class="{'spread':isSpread2}">
						<li @click="typeChange('all')" class="type-item" :class="{ 'is-actived': orderType == 'all' }">全部订单</li>
						<li  @click="typeChange('hotel')" class="type-item" :class="{ 'is-actived': orderType == 'hotel' }">酒店订单</li>
						<li  @click="typeChange('spot')" class="type-item" :class="{ 'is-actived': orderType == 'spot' }">景点订单</li>
						<li  @click="typeChange('rental')" class="type-item" :class="{ 'is-actived': orderType == 'rental' }">租车订单</li>
						<li  @click="typeChange('line')" class="type-item" :class="{ 'is-actived': orderType == 'line' }">线路订单</li>
					</ul>
				</div>
				<ul class="state-menu flex">
					<li  @click="stateChange('all')" class="state-item" :class="{ 'is-actived': orderState == 'all' }">全部</li>
					<li  @click="stateChange('unpaied')" class="state-item" :class="{ 'is-actived': orderState == 'unpaied' }">待付款</li>
					<li  @click="stateChange('completed')" class="state-item" :class="{ 'is-actived': orderState == 'completed' }">已完成</li>
					<li  @click="stateChange('closed')" class="state-item" :class="{ 'is-actived': orderState == 'closed' }">已关闭</li>
				</ul>
			</div>
			<ul class="order-list">
				<li class="order-item" v-for="i in 4">
					<div class="item-t flex flex-ver flex-jcsb">
						<p>
							<img class="icon" src="../../assets/images/icon-car.png" alt="">
							<span class="date">2019-10-30 17:50</span>
						</p>
						<span class="state">
							已支付
						</span>
					</div>
					<div class="item-m flex">
						<img src="../../assets/images/Hotel_img03.jpg" alt="" class="img">
						<div class="infos">
							<p class="title">
								可自选双人或3人套餐玩遍海洋王国看马戏，入住期间享横琴湾
								可自选双人或3人套餐玩遍海洋王国看马戏，入住期间享横琴湾
							</p>
							<span class="car">
								丰田 RAV4
							</span>
						</div>
					</div>
					<p class="item-b">
						<span class="label">总额</span>
						<span class="label">
							￥299.00
						</span>
						<span class="fr">
							<button class="m-btn">详情</button>
							<button class="m-btn">取消</button>
							<button class="m-btn m-btn-pay">支付</button>
						</span>
					</p>
				</li>
			</ul>
	</div>
</template>

<script>
export default {
	created() {
	},
	mounted() {},
	data() {
		return {
			currentTypeText:'全部订单',
			isSpread1:false,
			isSpread2:false,
			// limit: 1,
			// current_page: 1,
			// total_page: 99,
			orderType:'all',
			orderState: 'all'
		};
	},
	computed: {},
	watch: {
		'$route.query': function(newVal, oldVal) {
			console.log('oldVal' + oldVal.page);
			console.log('newVal' + newVal.page);
		}
	},
	methods: {
		typeChange(type) {
			this.currentTypeText = event.currentTarget.innerHTML.trim();
			this.isSpread = false;
			this.orderType = type;
		},
		stateChange(state) {
			this.orderState = state;
		}
	}
};
</script>

<style></style>

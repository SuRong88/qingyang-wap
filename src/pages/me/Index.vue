<template>
	<div class="me-index">
		<div class="me-index-banner flex flex-center">
			<div class="avatar-box">
				<img class="avatar" src="../../assets/images/avatar.png" alt="" />
				<p class="name">4646464646</p>
			</div>
		</div>
		<ul>
			<router-link to="/me/information" tag="li" class="menu-item flex flex-ver">
				<img class="icon" src="../../assets/images/me_icon01.png" alt="" />
				<span class="item-txt">个人信息</span>
			</router-link>
			<router-link to="/me/order/all" tag="li" class="menu-item flex flex-ver">
				<img class="icon" src="../../assets/images/me_icon02.png" alt="" />
				<span class="item-txt">我的订单</span>
			</router-link>
			<li @click="logoutHandle" class="menu-item flex flex-ver">
				<img class="icon" src="../../assets/images/me_icon03.png" alt="" />
				<span class="item-txt">退出登录</span>
			</li>
		</ul>
	</div>
</template>

<script>
export default {
	created() {
		this.$emit('curentIndexChange', 'meIndex');
	},
	mounted() {},
	data() {
		return {};
	},
	computed: {},
	watch: {},
	methods: {
		logoutHandle(){
			
		}
	}
};
</script>

<style></style>

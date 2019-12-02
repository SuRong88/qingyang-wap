<template>
	<div class="setting">
		<template v-if="!success">
			<div class="back-box"><img class="back-icon" src="../assets/images/login_Return.png" alt="" /></div>
			<div class="main-box">
				<h1 class="title">设置密码</h1>
				<input placeholder="输入密码" type="password" class="input" v-model="pwd1" />
				<input placeholder="确认密码" type="password" class="input" v-model="pwd2" />
				<button class="btn btn-confirm" @click="confirmHandle">确定</button>
			</div>
			<!-- <a href="tel:400-0000-000" class="tel-box flex flex-ver flex-align-center">
				<img src="../assets/images/login_icon.png" alt="" class="tel-icon" />
				<span class="tel-txt">客服热线：</span>
				<span class="tel">400-0000-000</span>
			</a> -->
		</template>
		<div v-else class="success flex flex-col flex-ver">
			<img class="success-icon" src="../assets/images/success-icon.png" alt="" />
			<h2 class="success-txt">密码设置成功</h2>
			<p class="tip2 text-c">{{ second }}秒后返回登录页面,重新登录</p>
			<router-link class="btn-back" tag="button" to="/login">返回登录页</router-link>
		</div>
	</div>
</template>

<script>
export default {
	created() {},
	mounted() {},
	data() {
		return {
			pwd1: '',
			pwd2: '',
			// 密码设置成功
			success: 1,
			// 倒计时
			second: 3
		};
	},
	computed: {},
	watch: {},
	methods: {
		confirmHandle() {}
	}
};
</script>

<style></style>

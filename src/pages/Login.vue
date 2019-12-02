<template>
	<div class="login">
		<div class="back-box">
			<img class="back-icon" src="../assets/images/login_Return.png" alt="">
		</div>
		<div class="main-box">
			<h1 class="title">用户登录</h1>
			<input placeholder="手机号" type="text" class="input" v-model="phone" />
			<input placeholder="密码" type="password" class="input" v-model="pwd" />
			<div class="code-box flex flex-ver flex-jcsb">
				<input placeholder="验证码" type="text" class="input input-code" v-model="code" />
				<img class="code-pic" src="../assets/images/login_pic.jpg" alt="" />
			</div>
			<div class="others clearfix">
				<router-link class="register-txt fl" to="/register">立即注册</router-link>
				<router-link class="forget-txt fr" to="/forget">忘记密码？</router-link>
			</div>
			<button class="btn btn-login" @click="loginHandle">登录</button>
		</div>
		<a href="tel:400-0000-000" class="tel-box flex flex-ver flex-align-center">
			<img src="../assets/images/login_icon.png" alt="" class="tel-icon">
			<span class="tel-txt">客服热线：</span>
			<span class="tel">400-0000-000</span>
		</a>
	</div>
</template>

<script>
export default {
	created() {},
	mounted() {},
	data() {
		return {
			phone: '',
			pwd: '',
			code: ''
		};
	},
	computed: {},
	watch: {},
	methods: {
		loginHandle() {}
	}
};
</script>

<style></style>

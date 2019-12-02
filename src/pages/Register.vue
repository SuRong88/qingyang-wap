<template>
	<div class="register">
		<div class="back-box">
			<img class="back-icon" src="../assets/images/login_Return.png" alt="">
		</div>
		<div class="main-box">
			<h1 class="title">用户注册</h1>
			<input placeholder="手机号码" type="text" class="input" v-model="phone" />
			<div class="code-box1 flex flex-ver flex-jcsb">
				<input placeholder="短信验证码" type="text" class="input" v-model="code1" />
				<span class="get-code" @click="getCode">获取验证码</span>
			</div>
			<button class="btn btn-register" @click="registerHandle">注册</button>
			<div class="others">
				<router-link class="login-txt" to="/login">账号密码登录</router-link>
			</div>
		</div>
		<a href="tel:400-0000-000" class="tel-box flex flex-ver flex-align-center">
			<img src="../assets/images/login_icon.png" alt="" class="tel-icon">
			<span class="tel-txt">客服热线：</span>
			<span class="tel">400-0000-000</span>
		</a>
		<v-mask :layerData="layerData" @layer-close="closeHandle" @layer-no="cancelHandle" @layer-yes="confirmHandle">
			<div class="code-box2 flex flex-ver">
				<input placeholder="点击验证码可更换" type="text" class="input-code2" v-model="code2" />
				<img class="code-pic" src="../assets/images/login_pic.jpg" alt="" />
			</div>
		</v-mask>
	</div>
</template>

<script>
// import vMask from 'components/mask/mask.vue';
export default {
	components: {
		vMask(resolve) {
			return require(['@/components/mask/mask.vue'], resolve);
		}
	},
	created() {
		// this.warnToast('该账号已存在，请通过找回密码或直接登录');
	},
	mounted() {},
	data() {
		return {
			phone: '',
			// 短信验证码
			code1: '',
			// 图形码
			code2: '',
			// 图形码模态框
			layerData: {
				isLayer: true, // 弹窗是否渲染
				isHeader: true, // 头部是否渲染
				isBtn: true, // 按钮是否渲染
				tit: '输入图像验证码', // 标题内容
				yes: '确定', // 确定按钮文本
				no: '取消', // 取消按钮文本
				isNo: true, // 是否需要取消按钮
				isClose: true // 是否需要关闭按钮
			}
		};
	},
	computed: {},
	watch: {},
	methods: {
		getCode() {
			this.layerData.isLayer = true;
		},
		closeHandle() {
			this.layerData.isLayer = false;
		},
		confirmHandle() {
			this.layerData.isLayer = false;
		},
		cancelHandle() {
			this.layerData.isLayer = false;
		},
		registerHandle() {}
	}
};
</script>

<style lang="less">
.register {
	.layer_con {
		display: flex;
		justify-content: center;
		align-items: center;
	}
}
</style>

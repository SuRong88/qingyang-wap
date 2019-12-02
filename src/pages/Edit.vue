<template>
	<div class="edit wrapper">
		<v-header :headerTitle="success?'操作成功':$route.meta.title"></v-header>
		<template v-if="!success">
			<ul>
				<li class="flex">
					<label for="pwd0">旧密码</label>
					<input  id="pwd0" placeholder="旧密码" type="password" class="input" v-model="pwd0" />
				</li>
				<li class="flex">
					<label for="pwd1">新密码</label>
					<input id="pwd1" placeholder="新密码" type="password" class="input" v-model="pwd1" />
				</li>
				<li class="flex">
					<label for="pwd2">确认密码</label>
					<input id="pwd2" placeholder="再次输入新密码" type="password" class="input" v-model="pwd2" />
				</li>
			</ul>
			<button :class="{yes:pwd0!=''&&pwd1!=''&&pwd2!=''}" class="btn btn-confirm" @click="confirmHandle">确定</button>
		</template>
		<div v-else class="success flex flex-col flex-ver">
			<img class="success-icon" src="../assets/images/success-icon.png" alt="" />
			<h2 class="success-txt">密码设置成功</h2>
			<p class="tip2 text-c">{{ second }}秒后返回登录页面,重新登录</p>
			<router-link class="btn btn-back" tag="button" to="/login">返回登录页</router-link>
		</div>
	</div>
</template>

<script>
import vHeader from 'components/common/Header.vue';
export default {
	components:{
		vHeader,
	},
	created() {},
	mounted() {},
	data() {
		return {
			// 旧密码
			pwd0: '',
			// 新密码
			pwd1: '',
			// 确认新密码
			pwd2: '',
			// 密码修改成功
			success: true,
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

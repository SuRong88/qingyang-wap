<template>
	<div class="header">
		<img class="icon-back" src="../../assets/images/header_Return.png" alt="" />
		<p class="h-title">
			{{headerTitle?headerTitle:'清扬会务'}}
		</p>
		<img @click="isSpread = !isSpread" class="icon-more" src="../../assets/images/header_more.png" alt="" />
		<ul class="nav" :class="{ spread: isSpread }">
			<router-link to="/index" tag="li" class="nav-item flex flex-ver">
				<img class="icon" src="../../assets/images/more_home.png" alt="" />
				<span>首页</span>
			</router-link>
			<router-link to="/me/index" tag="li" class="nav-item flex flex-ver">
				<img class="icon" src="../../assets/images/more_me.png" alt="" />
				<span>个人中心</span>
			</router-link>
		</ul>
	</div>
</template>

<script>
export default {
	name: 'vHeader',
	components: {},
	created() {},
	mounted() {},
	props: {
		headerTitle:String
	},
	data() {
		return {
			isSpread: false
		};
	},
	computed: {},
	watch: {},
	methods: {}
};
</script>

<style></style>

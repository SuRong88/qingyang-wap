<template>
	<div class="detail-page">
		<!-- 标题待修改 -->
		<v-header :headerTitle="isIntroduce?'会议介绍':'其他内容'"></v-header>
		<h1 class="title">这里是标题啊</h1>
		<div class="edit_textBox">
			<!-- 富文本 -->
		</div>
	</div>
</template>

<script>
import vHeader from 'components/common/Header.vue';
export default {
	components: {
		vHeader
	},
	created() {
		// 会议介绍 、其他内容
		this.isIntroduce = this.$route.params.type=='introduce';
	},
	mounted() {},
	data() {
		return {
			// 
			isIntroduce:true
		};
	},
	computed: {},
	watch: {},
	methods: {}
};
</script>

<style></style>

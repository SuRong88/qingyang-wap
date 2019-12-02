<template>
	<div class="index">
		<ul class="menu flex flex-align-center">
			<router-link class="menu-item" tag="li" to="/me/index"></router-link>
			<router-link class="menu-item" tag="li" to="/me/index"></router-link>
			<router-link class="menu-item" tag="li" to="/me/index"></router-link>
		</ul>
	</div>
</template>

<script>
export default {
	created() {
		console.log(window.$API);
	},
	mounted() {},
	data() {
		return {};
	},
	computed: {},
	watch: {},
	methods: {}
};
</script>

<style></style>

<template>
	<div class="hotel-box">
		<v-header :headerTitle="$route.meta.title"></v-header>
		<ul class="hotel-list">
			<router-link :to="'hotelDetail/'+ i" tag="li" v-for="i in 5" class="hotel-list-item flex">
				<img class="h-img" src="@/assets/images/banner01.png" />
				<div class="h-info">
					<p class="h-tit">{{i}}长隆横琴湾酒店(珠海海洋王国店)</p>
					<div class="h-type">
						<p>西式餐厅</p>
						<p>室外游泳池</p>
						<p>健身房</p>
						<p>室内游泳池</p>
						<p>娱乐场所</p>
						
					</div>
					<div class="h-bottom flex flex-jcsb flex-end">
						<p class="address flex flex-end">
							<img class="icon-address" src="../assets/images/home-icon.png" alt="" />
							珠海市横琴新区富祥湾
						</p>
						<span class="price">1300</span>
					</div>
				</div>
			</router-link>
		</ul>
		<div class="no-more flex flex-ver flex-align-center">
			暂无更多
		</div>
	</div>
</template>

<script>
import vHeader from 'components/common/Header.vue';
export default {
	components: {
		vHeader
	},
	created() {},
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

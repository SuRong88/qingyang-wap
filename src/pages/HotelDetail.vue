<template>
	<div class="hotelDe-box">
		<div class="h-banner">
			<swiper :options="SwiperOption1" ref="Swiper1">
				<swiper-slide v-for="(item, index) in imgList">
					<a href="javascript:;" class="s-img" @click=""><img class="banner-img" :src="item" /></a>
				</swiper-slide>
			</swiper>
			<span class="current-img-index">{{ currentIndex1 }}/{{ imgList.length }}</span>
		</div>
		<div class="info-box mb1">
			<p class="info-tit">长隆横琴湾酒店(珠海海洋王国店)</p>
			<p class="info-brief">
				<span>2014年开业</span>
				<span class="spe"></span>
				<span>三星级酒店/舒适</span>
			</p>
			<ul class="equipments clearfix">
				<li class="flex flex-ver" v-for="i in 5">
					<img class="icon-hotel" src="../assets/images/Hotel_icon02.png" alt="" />
					酒店各处
				</li>
			</ul>
			<div class="address-box flex flex-ver">
				<img class="icon-address" src="../assets/images/home-icon.png" alt="" />
				广东省珠海市横琴新区富祥湾
			</div>
		</div>
		<div class="date-box mb1" id="enter">
			<div class="enter-box flex flex-end flex-jcsb">
				<p style="color: #777;">
					<span class="enter-date">10月31日</span>
					<span>周四入住</span>
					<span class="enter-date">10月31日</span>
					周五离店
				</p>
				<p class="flex flex-ver">
					<span class="total">共一晚</span>
					<span class="arrow-right-icon"></span>
				</p>
			</div>
			<ul class="room-box">
				<li class="room-item flex" @click="viewRoom">
					<img class="img" src="../assets/images/Hotel_img02.jpg" alt="" />
					<div class="room-info flex flex-jcsb">
						<div class="room-l">
							<p class="room-tit flex flex-ver">
								商务大床房
								<span class="arrow-right-icon"></span>
							</p>
							<p class="room-s">
								<span>30㎡</span>
								<span>大床1.8米</span>
								<span>内窗</span>
							</p>
						</div>
						<div class="room-r clearfix">
							<span class="price fr">1300</span>
							<br />
							<span class="btn-order fr">预定</span>
						</div>
					</div>
				</li>
			</ul>
		</div>
		<ul class="more-info-box mb1">
			<li class="more-info-item">
				<h2 class="more-info-item-title">酒店简介</h2>
				<div class="more-info-item-content edit_textBox">
					酒店简介富文本
					<br />
					酒店简介富文本
					<br />
					酒店简介富文本
				</div>
			</li>
			<li class="more-info-item">
				<h2 class="more-info-item-title">联系酒店</h2>
				<div class="more-info-item-content edit_textBox">联系电话：0756-2998888</div>
			</li>
			<li class="more-info-item">
				<h2 class="more-info-item-title">酒店介绍</h2>
				<div class="more-info-item-content edit_textBox"><img src="../assets/images/Str_pic01.jpg" alt="" /></div>
			</li>
		</ul>
		<ul class="more-info-box mb1">
			<li class="more-info-item">
				<h2 class="more-info-item-title">附加费用</h2>
				<div class="more-info-item-content edit_textBox">
					富文本
					<br />
					富文本
					<br />
					富文本
				</div>
			</li>
		</ul>
		<ul class="more-info-box mb1">
			<li class="more-info-item">
				<h2 class="more-info-item-title">设施服务</h2>
				<div class="more-info-item-content">
					<div class="sub-content-box">
						<h3 class="sub-title">网络设施</h3>
						<div class="sub-content">
							<span class="sub-item flex flex-ver">
								<img class="sub-icon" src="../assets/images/Hotel_icon01.png" alt="" />
								酒店各处提供wifi
							</span>
						</div>
					</div>
					<div class="sub-content-box ">
						<h3 class="sub-title">酒店设施</h3>
						<div class="sub-content">
							<span v-for="i in 10" class="sub-item w33 flex flex-ver">
								<img class="sub-icon" src="../assets/images/Hotel_icon01.png" alt="" />
								西式餐厅
							</span>
						</div>
					</div>
				</div>
			</li>
		</ul>
		<ul class="more-info-box mb1">
			<li class="more-info-item">
				<h2 class="more-info-item-title">服务项目</h2>
				<div class="more-info-item-content edit_textBox">
					富文本
					<br />
					富文本
					<br />
					富文本
				</div>
			</li>
		</ul>
		<ul class="more-info-box mb1">
			<li class="more-info-item">
				<h2 class="more-info-item-title">交通指南</h2>
				<div class="more-info-item-content edit_textBox">
					富文本
					<br />
					富文本
					<br />
					富文本
				</div>
			</li>
		</ul>
		<ul class="more-info-box mb1">
			<li class="more-info-item">
				<h2 class="more-info-item-title">注意事项</h2>
				<div class="more-info-item-content edit_textBox">
					富文本
					<br />
					富文本
					<br />
					富文本
				</div>
			</li>
		</ul>
		<ul class="more-info-box">
			<li class="more-info-item">
				<h2 class="more-info-item-title">周边景点</h2>
				<div class="more-info-item-content edit_textBox">
					富文本
					<br />
					富文本
					<br />
					富文本
				</div>
			</li>
		</ul>
		<div class="fix-footer flex">
			<a class="fix-footer-l" href="tel:400 000 000">
				<img class="iocn-tel" src="../assets/images/icon.png" alt="" />
				电话客服
			</a>
			<a href="#enter" class="fix-footer-r">选择房型</a>
		</div>
		<v-slideUp :isLayer="isLayer" @closeHandle="isLayer = false">
			<div class="room-banner">
				<swiper :options="SwiperOption2" ref="Swiper2">
					<swiper-slide v-for="(item, index) in roomImgList"><img class="room-img" :src="item" /></swiper-slide>
				</swiper>
				<span class="current-img-index">{{ currentIndex2 }}/{{ roomImgList.length }}</span>
			</div>
			<ul class="room-info-box">
				<li class="room-info-item">
					<h3 class="info-item-tit">房型详情</h3>
					<div class="info-item-dv">
						<p>
							<span class="label">窗户:</span>
							有窗
						</p>
						<p>
							<span class="label">床型:</span>
							大床1.8米
						</p>
						<p>
							<span class="label">宽带:</span>
							wifi
						</p>
						<p>
							<span class="label">面积:</span>
							30㎡
						</p>
						<p>
							<span class="label">餐标:</span>
							单灿
						</p>
						<p>
							<span class="label">楼层:</span>
							12层
						</p>
					</div>
				</li>
				<li class="room-info-item">
					<h3 class="info-item-tit">房间设施</h3>
					<div class="info-item-dv info-item-dv2">
						<p>
							浴室
						</p>
						<p>
							拖鞋,24小时热水,
						</p>
					</div>
				</li>
			</ul>
			<div class="room-footer flex">
				<div class="room-footer-l" href="tel:400 000 000">
					<span class="price">1300</span>
				</div>
				<div  class="room-footer-r">立即预定</div>
			</div>
		</v-slideUp>
	</div>
</template>

<script>
import VSlideUp from 'components/mask/slideUp.vue';
export default {
	components: {
		VSlideUp
	},
	beforeCreate() {},
	created() {},
	mounted() {},
	destroyed() {},
	data() {
		return {
			// 房间信息弹窗
			isLayer: true,
			// 待
			currentRoom: {},
			// 当前banner轮播图索引+1
			currentIndex1: 1,
			// banner轮播图列表
			imgList: [
				require('@/assets/images/banner01.png'),
				require('@/assets/images/top-bar.png'),
				require('@/assets/images/banner01.png'),
				require('@/assets/images/top-bar.png'),
				require('@/assets/images/banner01.png'),
				require('@/assets/images/top-bar.png')
			],
			// 房间信息
			currentIndex2: 1,
			// 房间信息轮播图列表
			roomImgList: [
				require('@/assets/images/banner01.png'),
				require('@/assets/images/top-bar.png'),
				require('@/assets/images/banner01.png'),
				require('@/assets/images/top-bar.png'),
				require('@/assets/images/banner01.png'),
				require('@/assets/images/top-bar.png')
			],
			// banner轮播图配置
			SwiperOption1: {
				slidesPerView: 'auto',
				on: {
					slideChangeTransitionEnd: () => {
						this.currentIndex1 = this.swiper1.activeIndex + 1; //切换结束时，告诉我现在是第几个slide
					}
				}
			},
			// 房间信息轮播图配置
			SwiperOption2: {
				slidesPerView: 'auto',
				on: {
					slideChangeTransitionEnd: () => {
						this.currentIndex2 = this.swiper2.activeIndex + 1; //切换结束时，告诉我现在是第几个slide
					}
				},
				spaceBetween: 6
			}
		};
	},
	computed: {
		swiper1() {
			return this.$refs.Swiper1.swiper;
		},
		swiper2() {
			return this.$refs.Swiper2.swiper;
		}
	},
	watch: {},
	methods: {
		// 关闭弹窗
		closeHandle() {
			this.layerData.isLayer = false;
		},
		//查看房间类型
		viewRoom() {
			this.isLayer = true;
			// alert('查看房间')
		}
	}
};
</script>

<style></style>

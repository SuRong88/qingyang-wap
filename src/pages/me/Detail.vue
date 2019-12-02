<template>
	<div class="me-detail">
		<v-header :headerTitle="$route.meta.title"></v-header>
		<div class="state-box flex flex-ver flex-jcsb" :class="{ 'is-closed': false }">
			<div class="l">
				<span style="margin-right: 1rem;">订单状态:</span>
				<span class="state">待支付</span>
			</div>
			<div class="r">
				<span class="downtime flex flex-ver">
					<img class="icon-time" src="../../assets/images/time.png" alt="" />
					29:34
				</span>
				<span class="desc">订单保留时长</span>
			</div>
		</div>
		<div class="order-box">
			<span class="label">订单编号:</span>
			<span class="order-num">GP6366132944968359936</span>
		</div>

		<div class="info-box info-box01">
			<!-- 1酒店订单 -->
			<div class="sub-box" v-if="orderType == 'hotel'">
				<div class="sub-t flex flex-jcsb">
					<img class="img" src="../../assets/images/Hotel_img04.jpg" alt="" />
					<div class="infos">
						<p class="name">长隆横琴湾酒店(珠海海洋王国店)</p>
						<p class="desc">商务大床房</p>
					</div>
				</div>
				<ul class="sub-b">
					<li class="flex flex-ver flex-wrap">
						大床1.8米
						<span class="spe"></span>
						服务1
						<span class="spe"></span>
						服务2
						<span class="spe"></span>
						服务3
						<span class="spe"></span>
						服务3
						<span class="spe"></span>
						服务3
						<span class="spe"></span>
						服务3
						<span class="spe"></span>
						服务3
						<span class="spe"></span>
						服务3
						<span class="spe"></span>
						服务3
						<span class="spe"></span>
						服务3
					</li>
					<li class="flex flex-ver">
						入住
						<span class="date">10月31日</span>
						<span class="time">1晚</span>
						离店
						<span class="date">10月31日</span>
					</li>
					<li class="flex flex-jcsb">
						<span class="">2019-10-30</span>
						<p>
							￥
							<span class="price-mini">1000.00</span>
							X
							<span class="count">2</span>
							间
						</p>
					</li>
					<li class="flex flex-jcsb">
						<span>总计</span>
						<span class="price">￥2000.00</span>
					</li>
				</ul>
			</div>
			<!-- 2.景点订单/租车订单 -->
			<div class="sub-box" v-if="orderType == 'spot' || orderType == 'rental'">
				<div class="sub-t flex flex-jcsb">
					<img class="img" src="../../assets/images/Hotel_img04.jpg" alt="" />
					<div class="infos">
						<p class="name">长隆横琴湾酒店(珠海海洋王国店)</p>
						<p class="desc"></p>
					</div>
				</div>
				<ul class="sub-b sub-b02">
					<!-- 景点 -->
					<li v-if="orderType == 'spot'" class="flex flex-ver" style="margin-bottom: 1.4rem;">
						<span class="mr05">使用时间</span>
						<span class="date">2019-10-31</span>
					</li>
					<!-- 租车 -->
					<li v-else class="flex flex-ver flex-jcsb" style="margin-bottom: 1.4rem;">
						<p>
							<span class="mr05">用车日期</span>
							<span class="date">2019-10-31</span>
						</p>
						<p>
							<span class="mr05">还车日期</span>
							<span class="date">2019-10-31</span>
						</p>
					</li>
					<li class="flex flex-jcsb border0">
						<p>
							成人票
							<span class="ml1 mr1">（一天票）</span>
							(海洋王国)
						</p>
						<p>
							￥
							<span class="price-mini">1000.00</span>
							X
							<span class="count">2</span>
						</p>
					</li>
					<li class="flex flex-jcsb">
						<span>总计</span>
						<span class="price">￥2000.00</span>
					</li>
				</ul>
			</div>
			<!-- 3.线路订单 -->
			<div class="sub-box" v-else="orderType == 'line'">
				<div class="sub-t flex flex-jcsb">
					<img class="img" src="../../assets/images/Hotel_img04.jpg" alt="" />
					<div class="infos">
						<p class="name">长隆横琴湾酒店(珠海海洋王国店)</p>
						<p class="desc"></p>
					</div>
				</div>
				<ul class="sub-b sub-b03">
					<li class="flex flex-ver flex-jcsb">
						<!-- 样式一样使用相同类名 -->
						<span class="mr05">预定套餐</span>
						<span class="date">2天海洋王国游玩</span>
					</li>
					<li class="flex flex-ver flex-jcsb" style="margin-bottom: 1.4rem;">
						<span class="mr05">使用时间</span>
						<span class="date">2019-10-31</span>
					</li>
					<li v-for="i in 4" class="flex flex-jcsb border0">
						<p>成人</p>
						<p>
							￥
							<span class="price-mini">1000.00</span>
							X
							<span class="count">{{ i }}</span>
							人
						</p>
					</li>
					<li class="flex flex-jcsb">
						<span>总计</span>
						<span class="price">￥2000.00</span>
					</li>
				</ul>
			</div>
		</div>
		<div class="info-box info-box02">
			<div class="info-title">联系人信息</div>
			<ul class="info-bd">
				<li class="contact-item flex">
					<span class="label">联系人:</span>
					<span class="txt">某某人</span>
				</li>
				<li class="contact-item flex">
					<span class="label">手机号码:</span>
					<span class="txt"></span>
				</li>
				<li class="contact-item flex">
					<span class="label">电子邮箱:</span>
					<span class="txt">12</span>
				</li>
				<li class="contact-item flex">
					<span class="label">预定备注:</span>
					<span class="txt">备注信息</span>
				</li>
			</ul>
		</div>
		<div class="info-box info-box03">
			<div class="info-title">游客信息</div>
			<ul class="info-bd">
				<li v-for="i in 3" class="tourist-item flex flex-col flex-align-center">
					<span class="icon">游客{{ i }}</span>
					<p class="tourist-item-t">
						<span class="name">名字啊</span>
						<span class="=sex">男</span>
					</p>
					<p class="tourist-item-b">
						<span class="phone">15112001453</span>
						<span class="idcard">4504222000****2433</span>
					</p>
				</li>
			</ul>
		</div>
		<p class="order-date">
			<span class="mr05">下单时间:</span>
			<span class="mr05">2018-02-01</span>
			<span class="mr05">13:33:00</span>
		</p>
		<div class="pay-box flex flex-ver flex-jcsb">
			<p class="pay-l">
				<span class="label">总价</span>
				<span class="price">￥2000.00</span>
			</p>
			<p class="pay-r">
				<button type="button" class="p-btn" @click="layerData.isLayer = true">取消</button>
				<button type="button" class="p-btn p-btn-pay">支付</button>
			</p>
		</div>
		<v-mask :layerData="layerData" @layer-close="closeHandle" @layer-no="cancelHandle" @layer-yes="confirmHandle"><p class="tip">确定取消该订单？</p></v-mask>
	</div>
</template>

<script>
import vHeader from 'components/common/Header.vue';
export default {
	components: {
		vHeader,
		vMask(resolve) {
			return require(['@/components/mask/mask2.vue'], resolve);
		},
	},
	created() {
		// let validte = false
		// let orderTypeList = ['hotel','spot','rental','line'];
		// if(){}
		if (!(this.$route.params.type != '' && this.$route.params.id != '0')) {
			this.errorToast('缺少必要参数');
			return this.$router.replace({
				path: '/index'
			});
		}
		this.orderType = this.$route.params.type;
		console.log(this.$route.params);
		// this.$emit('curentIndexChange', 'meDetail');
	},
	mounted() {},
	data() {
		return {
			// 订单类型
			orderType: 'hotel',
			// 模态框
			layerData: {
				isLayer: 0, // 弹窗是否渲染
				isHeader: true, // 头部是否渲染
				isBtn: true, // 按钮是否渲染
				tit: '提示', // 标题内容
				yes: '确定', // 确定按钮文本
				no: '取消', // 取消按钮文本
				isNo: true, // 是否需要取消按钮
				isClose: false // 是否需要关闭按钮
			}
		};
	},
	computed: {},
	watch: {},
	methods: {
		closeHandle() {
			this.layerData.isLayer = false;
		},
		confirmHandle() {
			this.layerData.isLayer = false;
		},
		cancelHandle() {
			this.layerData.isLayer = false;
		}
	}
};
</script>

<style></style>

<template>
	<div class="me-information">
		<v-header :headerTitle="$route.meta.title"></v-header>
		<ul class="info-box"> 
			<li class="info-item flex flex-ver flex-jcsb">
				<span class="label">
					头像
				</span>
				<div class="avatar" :style="'background: url('+user.path+') center center/cover no-repeat;'">
					<input class="upload" type="file" accept="image/*" />
				</div>
			</li>
			<li class="info-item flex flex-ver flex-jcsb" @click="layerData.isLayer = true">
				<span class="label">
					用户名
				</span>
				<p class="info-txt">
					153*****38
				</p>
			</li>
			<li class="info-item flex flex-ver flex-jcsb">
				<span class="label">
					手机号
				</span>
				<p class="info-txt">
					153*****38
				</p>
			</li>
			<router-link to="/edit" tag="li" class="info-item flex flex-ver flex-jcsb">
				<span class="label">
					修改密码
				</span>
			</router-link>
		</ul>
		<v-mask :layerData="layerData" @layer-close="closeHandle" @layer-no="cancelHandle" @layer-yes="confirmHandle">
			<div class="input-box flex flex-ver">
				<input placeholder="请输入用户名" type="text" class="nickname" v-model="newName" />
			</div>
		</v-mask>
	</div>
</template>

<script>
import vHeader from 'components/common/Header.vue';
export default {
	components:{
		vHeader,
		vMask(resolve) {
			return require(['@/components/mask/mask2.vue'], resolve);
		}
	},
	created() {
		console.log(this.$API)
		this.$emit('curentIndexChange', 'meInformation');
	},
	mounted() {},
	data() {
		return {
			// 
			newName:'',
			// 
			user: {
				path:require('assets/images/avatar.png'),
				phone: '16464',
				name: '名字啊'
			},
			// 模态框
			layerData: {
				isLayer: false, // 弹窗是否渲染
				isHeader: true, // 头部是否渲染
				isBtn: true, // 按钮是否渲染
				tit: '修改用户名', // 标题内容
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
			if (this.nullTest(this.newName)) {
				return this.errorToast('用户名不能为空');
			}
			this.layerData.isLayer = false;
		},
		cancelHandle() {
			this.layerData.isLayer = false;
		},
	}
};
</script>

<style></style>

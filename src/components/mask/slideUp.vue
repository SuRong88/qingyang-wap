<template>
	<transition name="layer-trans">
		<section class="layer_box" v-if="isLayer">
			<div class="layer_sbox">
				<h1 class="layer_tit">
					标题
					<img @click="closeLayer" class="lay_close_icon" src="../../assets/images/close.png" alt="" />
				</h1>
				<div class="layer_con"><slot></slot></div>
			</div>
		</section>
	</transition>
</template>

<script>
export default {
	data() {
		return {};
	},
	props: {
		isLayer: Boolean
	},
	methods: {
		closeLayer() {
			this.$emit('closeHandle');
		}
	}
};
</script>

<style scoped lang="less">
.layer-trans-enter,
.layer-trans-leave-to {
	opacity: 0;
	.layer_sbox {
		transform: translateY(100%);
	}
}
.layer-trans-enter-active,
.layer-trans-leave-active,
.layer-trans-leave-active .layer {
	transition: all 0.2s linear;
	.layer_sbox {
		transition: all 0.2s linear;
	}
}

.layer-trans-leave-to .layer {
	transform: translateY(20%);
}

.layer_box {
	background: rgba(0, 0, 0, 0.5);
	display: table;
	height: 100%;
	width: 100%;
	position: fixed;
	top: 0;
	bottom: 0;
	left: 0;
	top: 0;
	z-index: 99999;
}
.layer_sbox {
	border-radius: 1.4rem 1.4rem 0 0;
	padding: 0 1.4rem;
	width: 100%;
	position: absolute;
	left: 0;
	bottom: 0;
	min-height: 50vh;
	// max-height: 80vh;
	background-color: #fff;
	display: table-cell;
	font-size: 0;
	line-height: 0;
	/*padding-bottom: 20%;*/
	text-align: center;
	vertical-align: middle;
}
.layer {
	background-color: #fff;
	-ms-border-radius: 0.6rem;
	-moz-border-radius: 0.6rem;
	-webkit-border-radius: 0.6rem;
	-o-border-radius: 0.6rem;
	border-radius: 0.6rem;
	display: inline-block;
	position: relative;
	min-width: 80vw;
	max-width: 85vw;
	overflow: hidden;
	padding: 3rem 0 0 0;
}
.layer_tit {
	text-align: left;
	color: #333;
	line-height: 5rem;
	font-weight: 700;
	font-size: 1.6rem;
	position: relative;
}
.lay_close_icon {
	width: 2.6rem;
	height: 2.6rem;
	float: right;
	position: absolute;
	top: 50%;
	right: 0rem;
	transform: translateY(-50%);
}
.layer_con {
	line-height: 2.2rem;
	font-size: 1.4rem;
	color: #555555;
	max-height: 75vh;
	overflow-y: auto;
}

.layer_con::-webkit-scrollbar {
	width: 0.5rem;
	height: 0.5rem;
	// width: 0;
}
.layer_con::-webkit-scrollbar-thumb {
	/*滚动条里面小方块*/
	-ms-border-radius: 0.5rem;
	-moz-border-radius: 0.5rem;
	-webkit-border-radius: 0.5rem;
	-o-border-radius: 0.5rem;
	border-radius: 0.5rem;
	-webkit-box-shadow: inset 0 0 0.5rem rgba(0, 0, 0, 0.7);
	background: rgba(0, 0, 0, 0.1);
}

.layer_btnbox {
	/*border-top: 1px solid #d2d3d5;*/
	font-size: 0;
	overflow: hidden;
	margin-top: 3rem;
}

.layer_btnbox a {
	-moz-box-sizing: border-box;
	-webkit-box-sizing: border-box;
	box-sizing: border-box;
	/*float: left;*/
	/*color: #fff;*/
	display: inline-block;
	font-size: 1.5rem;
	line-height: 5rem;
	text-align: center;
	width: 50%;
	border-top: 1px solid #e3e3e3;
}

.layer_yes {
	color: #ef4d06;
	border-left: 1px solid #e3e3e3;
}

.layer_no {
	color: #999999;
}

/*.layer_yes.on{width: 100%;}*/
.layer_close {
	position: absolute;
	top: 0.6rem;
	right: 0.6rem;
	width: 3rem;
}

.layer_close img {
	height: 3rem;
}
</style>

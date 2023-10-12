<template>

	<div class=" most-box">
		<div class="box-top">
			<div class="top-left" @click="openDialog('left')">
				<div class="top-left1">
					<image class="top-left2" :src="left.src||'../../static/gender.png'"></image>
				</div>
				<div class="top-left3">{{left.name || "请选择星座"}} </div>
			</div>
			<div class="top-center">
				<image class="top-center1" src="../../static/heart.png"></image>
			</div>

			<div class="top-right" @click="openDialog('right')">
				<div class="top-left1">
					<image class="top-left2" :src="right.src || '../../static/female.png'"></image>
				</div>
				<div class="top-left3">{{right.name || "请选择星座"}} </div>
			</div>
		</div>

		<div class="box-pair">
			<div class="pair-center">开始</div>
			<div class="pair-center1">
				<image class="pair-center2" src="../../static/love1.png"></image>
			</div>
			<div class="pair-center">配对</div>
		</div>
		<popup :showPop="dialog" @change="closeDialog">
			<div class="list">

				<div v-for=" end of arr " class="list-end" @click="getValue(end)">

					<div class="end-img">
						<image class="img" :src="end.src"></image>
					</div>
					<div class="text">{{end.name}}</div>
					<div class="date">{{end.date}}</div>
				</div>
				
			</div>
		</popup>
	</div>
</template>

<script>
	import * as base64 from "base-64"
	import asbod from '../../utils/crypto-js.js'
	import popup from '../../components/popup-layer.vue' //导入你要使用的组件
	import {
		list
	} from '../../config/star.js'

	export default {
		components: { //组件引入声明，必须是.vue结尾的组件才可以声明
			popup
		},
		data() { // 变量声明的地方 
			return {
				dialog: true,
				arr: [],
				left:{},
				right:{},
				current:"left"
			}
		},
		created() {
			this.arr = list //把数组list的东西传给arr数组
			console.log(this.arr)
		},
		methods: { //写函数的地方
		/*
		*  打开星座弹窗
		*/
			openDialog(type) {      //
				this.dialog = true  // 星座弹窗默认打开
				this.current = type  //是那边点击打开的星座弹窗
			},
			closeDialog(max) {
				this.dialog = max //点击不是星座的其他地方就关闭弹窗
			},
			getValue(value) {
				console.log(value)
				if(this.current==="left"){  //如果是左边星座打开
					this.left = value //选择里面的星座
				}
				else {//则是右边星座打开
					this.right = value//选择里面的星座
				}
				 this.dialog = false //点击选择的选择星座完毕弹窗关闭
			}
		},

	}
</script>

<style>
	.most-box {
		background-image: url(https://images.unsplash.com/photo-1513628253939-010e64ac66cd?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8OHx8c3RhcnxlbnwwfHwwfHx8MA%3D%3D&auto=format&fit=crop&w=800&q=60);
		width: 100vw;
		height: 100vh;
		background-size: 100% 100%;
	}

	.box-top {
		display: flex;
		justify-content: space-around;
		align-items: center;
		padding-top: 22px;
	}

	.top-left1 {
		border-radius: 50%;
		width: 50px;
		height: 50px;
		background-color: #4f708e59;
		padding: 14px 14px;
		margin: auto;
	}

	.top-left2 {
		width: 100%;
		height: 100%;
	}

	.top-left3 {
		width: 100px;
		font-size: 14px;
		color: #13dfc3;
		background-color: #4f708e59;
		border-radius: 10px;
		text-align: center;
		padding: 4px;
		margin-top: 8px;
	}

	.top-center1 {
		width: 70px;
		height: 70px;
	}

	.pair-center {
		color: #4836c3;
		font-size: 27px;
	}

	.pair-center2 {
		width: 30px;
		height: 30px;
		margin-top: 9px;
		padding: 0px 6px;
	}

	.box-pair {
		width: fit-content;
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: aqua;
		margin: 30px auto;
		border-radius: 11px;
		padding: 4px 21px
	}

	.list {
		display: flex;
		flex-wrap: wrap;
		margin-bottom: 12px;

	}

	.list-end {
		width: 33.33%;
		margin: 10px 0;
	}

	.end-img {
		background-color: #0e0d0d45;
		border-radius: 50%;
		width: 60px;
		height: 60px;
		display: flex;
		align-items: center;
		justify-content: center;
		margin: auto;


	}

	.img {
		width: 40px;
		height: 40px;
	}

	.text {
		text-align: center;
		font-size: 13px;
		color: #FFF;
	}

	.date {
		text-align: center;
		font-size: 13px;
		color: #FFF;
	}
</style>
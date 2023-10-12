<template>
	<div class="choose">
		<div class="left-back" @click="openDialog('left')">
			<div class="left">
				<image :src="leftImg"></image>
			</div>
			<div class="left-title">{{leftTitle}}</div>
		</div>

		<div class="center">
			<image src="../../static/heart.png"></image>
		</div>
		<div class="right-back" @click="openDialog('right')">
			<div class="right">
				<image :src="rightImg||'../../static/female.png'"></image>
			</div>
			<div class="right-title">{{rightTitle || "请选择星座"}}</div>
		</div>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				leftTitle: '',
				leftImg: '',
				rightTitle: '',
				rightImg: ''
			}
		},
		onLoad(query) {
			const {
				leftTitle,
				leftImg,
				rightTitle,
				rightImg
			} = query
			this.leftImg = leftImg
			this.leftTitle = leftTitle
			this.rightTitle = rightTitle
			this.rightImg = rightImg
		},
		methods: {

		}
	}
</script>

<style>
</style>
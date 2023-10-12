<template>
	<view class="content">
		<!-- <image class="header" src="/static/header.jpg"></image> -->
		<div class="header">
			<div class="title">
				<image src="../../static/title.png"></image>
			</div>
			<div class="font">热 | 门 ｜ 测 | 试 ｜ 为 | 您 ｜ 精 | 选</div>
		</div>
		<div class="list">
			<div class='item left' @click=detail(1)>
				<div>
					情感
				</div>
				<div class="icon-l">
					<image src="../../static/1.png"></image>
				</div>

			</div>
			<div class="item right" @click=detail(2)>
				<div>
					事业
				</div>
				<div class="icon-r">
					<image src="../../static/2.png"></image>
				</div>
			</div>
			<div class="item left-b" @click=detail(3)>
				<div>
					星座
				</div>
				<div class="icon-r">
					<image src="../../static/star.png"></image>
				</div>
			</div>
			<div class="item right-b" @click=detail(4)>
				<div>
					运势
				</div>
				<div class="icon-r">
					<image src="../../static/luck.png"></image>
				</div>
			</div>
		</div>
		<div class="line">
			<div class="icon-r">
				<image src="../../static/people.png"></image>
			</div>
			<div class="item-r">
				<div class="line-item">
					<div class="item-title">来测一测你以后适合什么工作</div>
					<div class="sub">给自己的未来一些职业方向建议</div>
				</div>
				<div class="right-icon">
					<image src="../../static/right.png"></image>
				</div>
			</div>
		</div>
		<div class="line">
			<div class="icon-r">
				<image src="../../static/love.png"></image>
			</div>
			<div class="item-r">
				<div class="line-item">
					<div class="item-title">来测一测你和他是否合适</div>
					<div class="sub">看看自己最适合的星座有哪些</div>
				</div>
				<div class="right-icon">
					<image src="../../static/right.png"></image>
				</div>
			</div>
		</div>
		<div class="line">
			<div class="icon-r">
				<image src="../../static/money.png"></image>
			</div>
			<div class="item-r">
				<div class="line-item">
					<div class="item-title">2023年财富运势解析</div>
					<div class="sub">全年财富运势的趋势大揭秘</div>
				</div>
				<div class="right-icon">
					<image src="../../static/right.png"></image>
				</div>
			</div>
		</div>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {
			detail(index) {
				if (index === 1) {
					uni.navigateTo({
						url: '/pages/matches/matches'
					})
				}
			}
		}
	}
</script>

<style>
	.content {
		text-align: center;
		margin: 0 20px;
	}

	.header {
		height: 146px;
		margin: auto;
		text-align: center;
		background: linear-gradient(to right, #7415ea, #8672d8);
		border-radius: 10px;
		width: 100%;
	}

	.title {
		width: 250px;
		height: 40px;
		margin: 0 auto;
		padding-top: 34px;
	}

	.font {
		font-size: 12px;
		color: #edb6ff;
		letter-spacing: 1px;
		padding-top: 16px;
	}


	.list {
		width: 100%;
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		color: #fff;
	}

	.item {
		width: 48%;
		height: 70px;
		border-radius: 16px;
		margin-top: 16px;
		display: flex;
		align-items: center;
		justify-content: space-around;
	}

	.left {
		background: linear-gradient(to left, #ffbfdfad, #f5424a)
	}

	.right {
		background: linear-gradient(to right, #dd7de8a6, #f9dff6b5)
	}

	.left-b {
		background: linear-gradient(to right, #d081f1, #f3d775a6)
	}

	.right-b {
		background: linear-gradient(to right, #ff8395, #f9efef)
	}

	.icon-l {
		width: 60px;
		height: 50px;
	}

	.icon-r {
		width: 40px;
		height: 42px;
	}

	image {
		width: 100%;
		height: 100%;
	}

	.line {
		margin-top: 20px;
		display: flex;
		justify-content: space-around;
		font-size: 12px;
		align-items: center;
		width: 100%;
		background-color: #efecff7d;
		border-radius: 10px;
		text-align: left;
		padding: 12px;
		box-sizing: border-box;
	}

	.item-title {
		font-size: 14px;
		font-weight: 600;
		margin-bottom: 6px;
		color: #333239;
	}

	.sub {
		color: #6961ad;
	}

	.right-icon {
		width: 20px;
		height: 20px;
	}

	.item-r {
		width: 70%;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
</style>
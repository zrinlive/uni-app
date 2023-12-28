<template>
	<view class="container">
		<view class="input-item">
			<u--input
				v-model="password"
				:type="isPassword ? 'password' : 'text'"
				placeholder="请输入密码"
				maxlength="20"
				color="#FFFFFF"
				@change="onInputChang"
				:password="isPassword"
				autocomplete="new-password"
			>
			</u--input>
			<view
				:style="{ 'background-color': isPassword ? 'red' : 'blue' }"
				@tap="togglePassword()"
				style="width: 40upx; height: 40upx; padding-top: 5upx"
			>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			password: "123456",
			isPassword: true, // 初始密码是否可见
		}
	},
	methods: {
		togglePassword() {
			// 点击切换密码可见性
			this.isPassword = !this.isPassword
		},

		onInputChang(e) {
			console.log("输入框", e)
		},
	},
}
</script>

<style lang="scss" scoped>

.container {
	padding-top: 238upx;
	box-sizing: border-box;
	position: relative;
	width: 100vw;
	overflow: hidden;
	// background: #507bfd;
}
.input-item {
	height: 75upx;
	margin-bottom: 50upx;
	position: relative;
	display: flex;
	-webkit-box-align: center;
	-webkit-align-items: center;
	align-items: center;
	background-color: #6c90ff;

	padding: 10upx 10upx;

	&:last-child {
		margin-bottom: 0;
	}

	.comp-name {
		font-size: 34upx;
		font-family: Source Han Sans CN;
		font-weight: 400;
		color: rgb(255, 255, 255);
		// flex: 1;
		margin-left: 16upx;
	}
}
</style>

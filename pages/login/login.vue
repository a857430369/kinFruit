<template>
	<view class="content">
			<view class="text-area">
				<form @submit="formSubmit" @reset="formReset">
					<view class="uni-form-item uni-column">
						<view class="title">用户名</view>
						<view>
							<input class="form_input" v-model="user_username" name="switch" />
					  </view>
						<view class="title">密码</view>
						<view>
							<input class="form_input" password v-model="user_password" name="switch" />
						</view>
					 </view>
				</form>
			</view>
			<view class="button_login">
				<button @click="getMessage">登录</button>
				<button @click="toRegister">注册</button>
			</view>
			<view :class="flag?'getErro':'notGetErro'">
				<text>用户名或密码输入错误</text>
			</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				user_username:'',
				user_password:'',
				flag: false
			}
		},
		methods: {
			toRegister() {
				uni.navigateTo({
					url:'../register/register'
				})
			},
			getMessage() {
				let form={
					user_username: this.user_username,
					user_password: this.user_password
				}
				uni.request({
					url:'http://localhost:8088/user/login',
					data:form,
					method: "POST"
				}).then((res) => {
					let code = res[res.length-1].data.code
					if(code !== 0){
						this.flag = true
					}else{
						uni.redirectTo({
							url:'../index/index'
						})
						this.flag = false
					}
				}).catch((erro) => {
					console.log(erro)
				})
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
	.form_input{
		padding: 15rpx;
		border:1rpx solid #000000;
	}
	.forget{
		margin-right: 200rpx;
	}
	.button_login{
		display: flex;
	}
	.getErro{
		color: red;
	}
	.notGetErro{
		display: none;
	}
</style>

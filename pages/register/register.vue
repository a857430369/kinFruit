<template>
	<view class="content_register">
		<view class="form_register">
			<form @submit="onSubmit" @reset="reset">
				<view class="title_input">用户名</view>
				<view style="border: 1px solid #000000;">
					<input name="user_username" />
				</view>
				<view class="title_input">密码</view>
				<view style="border: 1px solid #000000;">
					<input password name="user_password" />
				</view>
				<view class="title_input">真实姓名</view>
				<view style="border: 1px solid #000000;">
					<input name="user_realname" />
				</view>
				<view class="title_input">电话</view>
				<view style="border: 1px solid #000000;">
					<input name="user_phone" />
				</view>
				<view class="title_input">邮箱</view>
				<view style="border: 1px solid #000000;">
					<input name="user_email" />
				</view>
				<view class="button_register">
					<button form-type="submit">Submit</button>
					<button type="default" form-type="reset">Reset</button>
				</view>

			</form>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			onSubmit(e) {
				let form = e.detail.value
				form.user_type = "C"
				form.user_status = "H"
				uni.request({
					url: 'http://localhost:8088/user/register',
					data: form,
					method: "POST"
				}).then((res) => {
					if(res[res.length-1].data.code === 0){
						uni.redirectTo({
							url:'../login/login'
						})
					}
				}).catch((e) => {
					console.log(e)
				})
			},
			reset() {}
		}
	}
</script>

<style>
	.content_register {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.button_register {
		display: flex;
	}
</style>

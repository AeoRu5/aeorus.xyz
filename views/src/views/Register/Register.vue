<template>
	<div class="view_loginRegister_frame_app_ignore frameConfig">
		<div class="view_loginRegister_form_frame">
			<div class="view_loginRegister_form_title themeFontColorMain englishFont ac">WelCome To AeoRus~</div>
			<div class="view_loginRegister_form_body">
				<div class="view_loginRegister_form_tel view_loginRegister_form_input_block relative">
					<input
						v-model="register_tel"
						class="view_loginRegister_form_input"
						type="number"
						placeholder="请输入手机号">
				</div>
				<div class="view_loginRegister_form_tel view_loginRegister_form_input_block relative">
					<input
						v-model="register_nickname"
						class="view_loginRegister_form_input"
						type="text"
						placeholder="请输入昵称">
				</div>
				<div class="view_loginRegister_form_securityCode view_loginRegister_form_input_block relative">
					<input
						v-model="register_securityCode"
						class="view_loginRegister_form_input"
						type="number"
						placeholder="请输入验证码">
					<div
						class="view_loginRegister_form_securityCode_btn themeFontColorMain cp"
						:class="register_securityCode_isGetting ? 'view_loginRegister_form_securityCode_btn_isGetting' : ''"
						@click="_register_securityCode_get">{{register_securityCodeTxt}}</div>
				</div>
				<div class="view_loginRegister_form_password view_loginRegister_form_input_block relative">
					<input
						v-model="register_password"
						class="view_loginRegister_form_input"
						:type="register_password_type"
						placeholder="设置密码(6-20位字母数字组合)">
					<div
						v-if="!register_toggle_password_show"
						class="iconfont icon-eye themeFontColorMain cp"
						@click="_register_toggle_password_show"></div>
					<div
						v-else
						class="iconfont icon-eye-close themeFontColorMain cp"
						@click="_register_toggle_password_show"></div>
				</div>
				<div v-if="register_password_format_error_show" class="view_loginRegister_form_input_tip">
					<div class="iconfont icon-alert"></div>
					<div class="view_loginRegister_form_input_tip_message">{{register_password_format_error_message}}</div>
				</div>
				<div class="view_loginRegister_form_confirm themeBackgroundColorMain themeFontColorSub cp" @click="_register_confirm_register">注册</div>
				<router-link
					:to="{
						name: 'login',
						query: {
							redirect: $route.query.redirect
						}
					}"
					replace
					class="view_loginRegister_toEachOther_btn themeFontColorMain themeFontColorMain themeAfterBackgroundColor block relative ac cp">登录账号</router-link>
			</div>
		</div>
	</div>
</template>

<script src="./Register.js"></script>

<style scoped lang="less" src="../../assets/loginRegister.less"></style>
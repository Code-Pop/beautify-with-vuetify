<template>
	<v-card width="400" class="mx-auto mt-5">
		<v-card-title>
			<h1 class="display-1">Đăng nhập</h1>
		</v-card-title>
		<v-card-text>
			<v-form>
				<v-text-field label="Tên đăng nhập" prepend-icon="mdi-account-circle" />
				<v-text-field
					:type="showPassword ? 'text' : 'password'"
					label="Mật khẩu"
					prepend-icon="mdi-lock"
					:append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
					@click:append="showPassword = !showPassword"
				/>
			</v-form>
		</v-card-text>
		<v-divider></v-divider>
		<v-card-actions>
			<v-btn color="info">Đăng nhập</v-btn>
			<v-spacer></v-spacer>
			

		</v-card-actions>
	</v-card>
</template>

<script>
export default {
	name: 'LoginPage',
	data() {
		return {
			showPassword: false
		}
	}
}
</script>

<style></style>

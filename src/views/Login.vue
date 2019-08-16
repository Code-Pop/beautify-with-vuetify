<template>
	<v-card width="400" class="mx-auto mt-5">
		<v-card-title>
			<h1 class="display-1">Login</h1>
		</v-card-title>
		<v-card-text>
			<v-form>
				<v-text-field label="Username" prepend-icon="mdi-account-circle" />
				<v-text-field
					:type="showPassword ? 'text' : 'password'"
					label="Password"
					prepend-icon="mdi-lock"
					:append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
					@click:append="showPassword = !showPassword"
				/>
			</v-form>
		</v-card-text>
		<v-divider></v-divider>
		<v-card-actions>
			<v-btn color="success">Register</v-btn>
			<v-spacer></v-spacer>
			<v-btn color="info">Login</v-btn>
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

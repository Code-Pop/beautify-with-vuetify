<template>
	<v-app>
		<v-app-bar app color="primary" dark>
			<v-toolbar-title>Vuetify Dashboard</v-toolbar-title>
			<v-spacer></v-spacer>
			<v-btn text rounded>Home</v-btn>
			<v-btn text rounded>Login</v-btn>
		</v-app-bar>
		<v-content>
			<!-- Login Module -->
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
		</v-content>
		<v-footer color="primary lighten-1" padless>
			<v-layout justify-center wrap>
				<v-btn
					v-for="link in links"
					:key="link"
					color="white"
					text
					rounded
					class="my-2"
				>
					{{ link }}
				</v-btn>
				<v-flex primary lighten-2 py-4 text-center white--text xs12>
					{{ new Date().getFullYear() }} — <strong>Vuetify Dashboard</strong>
				</v-flex>
			</v-layout>
		</v-footer>
	</v-app>
</template>

<script>
export default {
	name: 'App',
	data() {
		return {
			showPassword: false,
			links: ['Home', 'Login']
		}
	}
}
</script>

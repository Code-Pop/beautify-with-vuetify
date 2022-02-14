<template>
	<v-container>
		<v-layout text-center wrap>
			<v-flex xs12>
				<v-img
					:src="require('../assets/logo.svg')"
					class="my-3"
					contain
					height="200"
				></v-img>
			</v-flex>

			<v-flex mb-4>
				<h1 class="display-2 font-weight-bold mb-3">
					DAU TU 101
				</h1>
				<p class="subheading font-weight-regular">
					Kết nối và đồng hành,
					<br />Cộng đồng Nhà đầu tư Telegram
					<a href="https://t.me/dautu101" target="_blank"
						>@dautu101</a
					>
				</p>
			</v-flex>

			<v-flex mb-5 xs12>
				<h2 class="headline font-weight-bold mb-3">Cách chúng tôi hỗ trợ bạn?</h2>

				<v-layout justify-center>
					<a
						v-for="(next, i) in whatsNext"
						:key="i"
						:href="next.href"
						class="subheading mx-3"
						target="_blank"
					>
						{{ next.text }}
					</a>
				</v-layout>
			</v-flex>

			<v-flex xs12 mb-5>
				<h2 class="headline font-weight-bold mb-3">Important Links</h2>

				<v-layout justify-center>
					<a
						v-for="(link, i) in importantLinks"
						:key="i"
						:href="link.href"
						class="subheading mx-3"
						target="_blank"
					>
						{{ link.text }}
					</a>
				</v-layout>
			</v-flex>

			<v-flex xs12 mb-5>
				<h2 class="headline font-weight-bold mb-3">Ecosystem</h2>

				<v-layout justify-center>
					<a
						v-for="(eco, i) in ecosystem"
						:key="i"
						:href="eco.href"
						class="subheading mx-3"
						target="_blank"
					>
						{{ eco.text }}
					</a>
				</v-layout>
			</v-flex>
		</v-layout>
	</v-container>
</template>

<script>
export default {
	data: () => ({
		ecosystem: [
			{
				text: 'vuetify-loader',
				href: 'https://github.com/vuetifyjs/vuetify-loader'
			},
			{
				text: 'github',
				href: 'https://github.com/vuetifyjs/vuetify'
			},
			{
				text: 'awesome-vuetify',
				href: 'https://github.com/vuetifyjs/awesome-vuetify'
			}
		],
		importantLinks: [
			{
				text: 'Documentation',
				href: 'https://vuetifyjs.com'
			},
			{
				text: 'Chat',
				href: 'https://community.vuetifyjs.com'
			},
			{
				text: 'Made with Vuetify',
				href: 'https://madewithvuejs.com/vuetify'
			},
			{
				text: 'Twitter',
				href: 'https://twitter.com/vuetifyjs'
			},
			{
				text: 'Articles',
				href: 'https://medium.com/vuetify'
			}
		],
		whatsNext: [
			{
				text: 'Cơ cấu lại danh mục miễn phí',
				href: 'https://dautu101.com'
			},
			{
				text: 'Tư vấn tạo danh mục tối ưu',
				href: 'https://dautu101.com'
			},
			{
				text: 'Các bài viết chia sẻ về kinh nghiệm đầu tư',
				href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions'
			}
		]
	})
}
</script>

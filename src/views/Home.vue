<template>
	<div class="home">
		<HelloWorld msg="ĐẦU TƯ 101" />
	</div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
	name: 'home',
	components: {
		HelloWorld
	}
}
</script>

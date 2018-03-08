<template>
	<div class="padding">
		<div class="column-large column-centered">
			<h1>Projects</h1>
			<componentCard></componentCard>
		</div>
	</div>
</template>

<script>
	import cards from './card.vue'

	export default {
		components: {
			componentCard: cards
		}
	}
</script>

<style scoped lang="scss">
	main {
		
	}
</style>
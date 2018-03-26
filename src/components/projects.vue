<template>
	<div class="padding">
		<div class="column-large column-centered">
			<h1>Projects</h1>
			<componentCard></componentCard>
			<p class="footnote">All projects shown were developed while employed by <a href="https://www.ntara.com/" target="_blank">Ntara</a>, a digital agency in Johnson City, Tennessee.</p>
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
	.footnote {
		margin-top: 24px;
	}
</style>
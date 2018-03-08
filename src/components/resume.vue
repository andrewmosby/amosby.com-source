<template>
	<div class="padding">
		<div class="column-small column-centered">
			<h1 class="printHide">Resumé</h1>
			<div v-if="view === 'copy'" class="printHide">
				<p>Thanks for taking the time to get to know me and how all of those life experiences connect. At any point, though, you can switch back to and print the more succinct format.</p>
				<button @click="view = 'list'">Give it to me straight</button>
			</div>
			<div v-if="view === 'list'" class="printHide">
				<p>As you can see, this is the <strong>traditional format</strong> of my resumé. But ingrained in every resumé are life experiences that mold us and shape us. If we take the time, our dry bulleted lists can be connected to form a vibrant picture of who we are today.</p>
				<button @click="view = 'copy'">Connect the dots for me</button>
			</div>
			<div class="contentEntry">
				<componentResumeCopy v-if="view === 'copy'" v-on:emitChangePage="changePage"></componentResumeCopy>
				<componentResumeList v-if="view === 'list'"></componentResumeList>
			</div>
			<div class="contentEntry">
				<p>Now that you've seen my resumé, feel free to <a @click="changePage('projects')">see some of my work</a>, read about my <a @click="changePage('philosophies')">front end values</a>, or get to know me <a @click="changePage('about')">just a little more personally</a>.</p>
			</div>
		</div>
	</div>
</template>

<script>
	import resumeList from './resume-list.vue'
	import resumeCopy from './resume-copy.vue'

	export default {
		data: function() {
			return {
				view: 'list'
			}
		},
		components: {
			componentResumeList: resumeList,
			componentResumeCopy: resumeCopy
		},
		methods: {
			changePage: function (pageName) {
				this.$emit('emitChangePage', pageName)
			}
		},
	}
</script>

<style lang="scss">
	@import "./../variables.scss";
	@import "./../mixins.scss";

	.resume_title {
		margin-bottom: 36px;
		text-align: center;

		h2 {
			margin-bottom: 8px;
		}
	}
	.hasOverline {
		&:before {
 			content: "";
    		display: block;
    		max-width: 40px;
    		margin: 0 0 8px;
    		height: 4px;
    		background: $colorBeige;
		}
	}
	@media print {
		.header, .footer, .headerToggle {
			display: none;
		}
		.contentEntry {
			margin-top: 0;
			padding: 16px 0;
		}
		.hasOverline:before {
			display: none;
		}
		.contentEntry p + h3, .contentEntry img + h3, .contentEntry ul + h3, .contentEntry p + ul {
			padding-top: 4px;
		}
	}
</style>
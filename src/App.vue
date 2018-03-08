<template>
	<div class="siteContainer">
		<appHeader v-on:emitChangePage="changePage"></appHeader>
		<appCoverLetter v-bind:class="{ active: showMenu }"></appCoverLetter>
		<div v-bind:class="{ active: showMenu }" @click="toggleHeader" class="headerToggle">
			<i class="headerToggle_icon icon-material">format_quote</i>
		</div>
		<main>
			<pageHome v-if="page === 'home'" v-on:emitChangePage="changePage"></pageHome>
			<pageProjects v-if="page === 'projects'"></pageProjects>
			<pageResume v-if="page === 'resume'" v-on:emitChangePage="changePage"></pageResume>
			<pagePhilosophies v-if="page === 'philosophies'"></pagePhilosophies>
			<pageAbout v-if="page === 'about'"></pageAbout>
		</main>
		<appFooter></appFooter>
	</div>
</template>

<script>
	import header from './components/header.vue'
	import coverLetter from './components/coverLetter.vue'
	import footer from './components/footer.vue'
	import home from './components/home.vue'
	import projects from './components/projects.vue'
	import resume from './components/resume.vue'
	import philosophies from './components/philosophies.vue'
	import about from './components/about.vue'

	export default {
		data: function() {
			return {
				page: 'home',
				showMenu: false
			}
		},
		mounted: function() {
			let getParameterByName = function(name, url) {
				if (!url) url = window.location.href;
				name = name.replace(/[\[\]]/g, '\\$&');
				var regex = new RegExp('[?&]' + name + '(=([^&#]*)|&|#|$)'),
					results = regex.exec(url);
				if (!results) return null;
				if (!results[2]) return '';
				return decodeURIComponent(results[2].replace(/\+/g, ' '));
			};

			var queryString = getParameterByName('page')
			if (queryString !== null) {
				this.page = queryString
				history.replaceState('', '', '?page=' + this.page);
			} else {
				this.page = 'home';
			}
		},
		methods: {
			changePage: function(newPage) {
				//change the page
				this.page = newPage

				//remove the header menu
				this.showMenu = false

				//scroll window to top
				window.scroll(0, 0)

				// Set query string for state management
				history.replaceState('', '', '?page=' + newPage);
			},
			toggleHeader: function() {
				if (this.showMenu == false) {
					this.showMenu = true
				} else {
					this.showMenu = false	
				}
			}
		},
		components: {
			appHeader: header,
			appCoverLetter: coverLetter,
			appFooter: footer,
			pageHome: home,
			pageProjects: projects,
			pageResume: resume,
			pagePhilosophies: philosophies,
			pageAbout: about
		}
	}
</script>

<style lang="scss">
	@import "./variables.scss";
	@import "./style.scss";

	// Material Design icons 
	@font-face {
		font-style: normal;
		font-weight: 400;
		font-family: "Material Icons";
		src: url("https://cdn.rawgit.com/google/material-design-icons/a6145e16/iconfont/MaterialIcons-Regular.eot");
		/* For IE6-8 */
		src: url("https://cdn.rawgit.com/google/material-design-icons/a6145e16/iconfont/MaterialIcons-Regular.woff2") format("woff2"), url("https://cdn.rawgit.com/google/material-design-icons/a6145e16/iconfont/MaterialIcons-Regular.woff") format("woff"), url("https://cdn.rawgit.com/google/material-design-icons/a6145e16/iconfont/MaterialIcons-Regular.ttf") format("truetype");
	}
	.icon-material {
		/* Preferred icon size */
		display: inline-block;
		font-style: normal;
		font-weight: normal;
		font-size: 24px;
		font-family: "Material Icons";
		text-transform: none;

		/* Support for all WebKit browsers. */
		-webkit-font-smoothing: antialiased;
		/* Support for Firefox. */
		-moz-osx-font-smoothing: grayscale;
		line-height: 1;
		letter-spacing: normal;
		word-wrap: normal;
		white-space: nowrap;
		direction: ltr;
		/* Support for Safari and Chrome. */
		text-rendering: optimizeLegibility;
		/* Support for IE. */
		font-feature-settings: "liga";
	}
	
	.headerToggle {
		position: fixed;
		top: 0;
		right: 0;
		width: 100px;
		height: 86px;
		padding: 12px;
		background: $colorBlack;
		text-align: center;
		font-family: $fontPrimary;
		text-transform: uppercase;
		color: $colorLightGray;
		cursor: pointer;
		z-index: 2000;
		
		&:after {
			content: "Cover Letter";
			display: block;
		    line-height: 1.2;
		}
		
		&.active {
		
			&:after {
				content: "Close";
			}
		}

		@media (max-width: $phoneMax) {
			display: none;
		}
	}
	.headerToggle_icon {
		display: block;
	}
	.contentEntry {
		$space: 80px;
		max-width: $elementMaxWidth + ($space*2);
		margin: $space auto 0 0;
		padding: $space;
		background: $colorBlack;
		color: $colorLightGray;

		h2 {
			text-align: center;
		}
		h3 {
			margin-bottom: $marginTopBottom*(1/2);
		}
		img {
			margin-bottom: $marginTopBottom;	
		}
		p, img, ul {
			+ h3 {
				padding-top: $marginTopBottom*(1/2);
			}
		}

		@media (max-width: $tabletMax) {
			margin-top: 60px;
			padding: 60px 32px;
		}

		@media (max-width: $phoneMax) {
			margin-top: 32px;
			padding: 32px 16px;
		}
	}
</style>
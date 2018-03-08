<template>
	<div>
		<img class="banner"  v-bind:src="bannerImg">
		<div class="padding background-darkGray">
			<div class="textAlign-center">
				<h1>Hi, I'm Andrew Mosby.</h1>
				<p>I am a Front End Developer with a background in design and I focus on user experience, performance, and maintainable code. I also enjoy growing teams by empowering individual contributors. I have significant experience collaborating with designers and back end developers as well as coming up with solutions with clients.</p>
				<p>One of my favorite aspects of working in web development is the open learning envirnoment we all share&mdash;we're all learning together as the web evolves. And I've been very fortunate to learn from and work with some fantastic and talented folks throughout the years.</p>
			</div>
			<div class="quoteWrapper">
				<blockquote class="quote">
					<p>Andrew is solid developer with a wide skill set. He's meticulous, loyal, positive, and articulate&mdash;with an incredible work ethic. A true collaborator...I trust him with my life.</p>
					<cite>Joshua Hathaway, Creative Director</cite>
				</blockquote>
				<blockquote class="quote">
					<p>As a back end developer, it's rare to work with a front end developer who is able to understand and work with my needs as they pertain to software development. Mosby can effectively communicate with anyone in the development chain.</p>
					<cite>Trent Sartain, Back End Developer</cite>
				</blockquote>
				<blockquote class="quote">
					<p>In a fast-paced agency with tight deadlines, I love that I can hand off a desktop design to Andrew and he can make design decisions about how to handle components responsively.</p>
					<cite>Mickey Brown, Art Director</cite>
				</blockquote>
				<blockquote class="quote">
					<p>I have learned and grown so much in two years of working with Andrew. I have really found my strengths as a developer and Andrew has trusted me to develop them for the betterment of the team.</p>
					<cite>Jonathan Davis, Front End Developer</cite>
				</blockquote>
			</div>
		</div>
		<div class="padding padding-remove-bottom background-black" style="overflow: hidden;">
			<div class="textAlign-center">
				<h1>Don't be a stranger.</h1>
				<p>Take a look around and get to know me. You'll find numerous work samples as well as some writing about what I care about both professionally and recreationally. If this isn't enough, check me out on <a href="//twitter.com/_andrewmosby">twitter</a> and <a href="//codepen.com/amosby">codepen</a>.</p>
				<span></span>
			</div>
		</div>
		<div class="iconGrid">
			<span class="iconGrid_link"></span>
			<a @click="changePage('projects')" class="iconGrid_link">
				<i class="icon-material iconGrid_icon">code</i>
				See my work
			</a>
			<a @click="changePage('resume')" class="iconGrid_link">
				<i class="icon-material iconGrid_icon">content_paste</i>
				View my resume
			</a>
			<span class="iconGrid_link"></span>
			<span class="iconGrid_link"></span>
			<a @click="changePage('philosophies')" class="iconGrid_link">
				<i class="icon-material iconGrid_icon">format_quote</i>
				Read my thoughts
			</a>
			<a @click="changePage('about')" class="iconGrid_link">
				<i class="icon-material iconGrid_icon">person_outline</i>
				Get to know me
			</a>
			<span class="iconGrid_link"></span>
		</div>
	</div>
</template>

<script>
	export default {
		data: function() {
			return {
					bannerImg: require('./../assets/home-banner.jpg')
			};
		},
		methods: {
			changePage: function (pageName) {
				this.$emit('emitChangePage', pageName)
			}
		}
	}

</script>

<style scoped lang="scss">
	@import "../variables.scss";
	.banner {
		display: block;
		width: 100%;
	}
	.iconGrid {
		display: -ms-grid;
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(22%, 1fr));
		grid-gap: 0;
		background: url(./../assets/iconGrid-background.jpg) no-repeat;
		background-size: cover;
		padding: 0;
	}
	.iconGrid_link {
		padding: 80px 20px;
		color: white;
		text-align: center;
		text-decoration: none;
		text-transform: uppercase;
		font-family: $fontPrimary;
		font-weight: 700;
	}
	.iconGrid_link:first-child, .iconGrid_link:nth-child(2), .iconGrid_link:nth-child(3), .iconGrid_link:nth-child(5), .iconGrid_link:nth-child(6), .iconGrid_link:nth-child(7) {
		border-right: 1px solid rgba(255,255,255,0.2);
	}
	.iconGrid_link:first-child, .iconGrid_link:nth-child(2), .iconGrid_link:nth-child(3), .iconGrid_link:nth-child(4) {
		border-bottom: 1px solid rgba(255,255,255,0.2);
	}
	a.iconGrid_link:hover {
		background: $colorDarkGray;
		color: $colorBeige;
		text-decoration: none;
		cursor: pointer;
	}
	.iconGrid_icon {
		display: block !important;
		margin-bottom: 12px;
		font-size: 36px;
		color: $colorLightGray;
	}
	@media (max-width: $tabletMax) {
		.iconGrid_link {
			padding-top: 60px;
			padding-bottom: 60px;
		}
	}
	@media (max-width: $phoneMax) {
		span.iconGrid_link {
			display: none;
		}
		.iconGrid {
			grid-template-columns: repeat(auto-fit, minmax(40%, 1fr));
		}
	}
	.quoteWrapper {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(45%, 1fr));
		grid-gap: 40px;
		margin: 48px auto 0;
		max-width: 1040px;
	}
	.quote {
		padding: 24px;
		background: $colorBlack;
		margin-bottom: 0;

	}
</style>
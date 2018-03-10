<template>
	<div class="padding coverLetter printHide">
		<div>
			<h2>{{ letter.title }}</h2>
			<p v-html="letter.copy"></p>
			<cite>~ {{ letter.author }}</cite>
		</div>
	</div>
</template>

<script>
	export default {
		data: function () {
			return {
				letter: {
					title: 'Cover Letter',
					copy: 
						"<p>If you have landed on this site, you have likely have some interest in hiring either an experienced Front End Developer or a Director of Front End Development. I have over eight years of development experience and well more than that in people organizing and motivating. I currently work in an established agency working for enterprise-level clients and with other talented developers. I have worked on 1000-page sites, 4-page boutique sites, and everything in between. I have also grown a department of front end developers by focusing on their professional development.</p>" + 
						"<p>Developers come to code from many places, but I bring a design-oriented attention to detail and a focus on growing a team by focusing on the strengths and interests of individuals. Whether I am contributing to a site's code base or planning for the growth of a department, you can expect a high degree of quality and focus.</p>" + 
						"<p>After going through my site and work examples, please contact me either by <a href='mailto:r.andrew.mosby@gmail.com'>sending an email</a> or via your normal application process.</p>" +
						"<p>Thank you,</p>",
					author: 'Andrew Mosby'
				}
			};
		}
	}
</script>

<style lang="scss">
	@import "../variables.scss";

	.coverLetter {
		position: fixed;
		display: flex;
		align-items: center;
		background: linear-gradient(to bottom, $colorDarkGray, #000);
		color: $colorLightGray;
		width: 100%;
		min-height: 100vh;
		overflow: hidden;
		transform: translateY(-100%);
		transition: $transition;
		z-index: 1000;

		&.active {
			transform: translateY(0);
		}
	}

</style>
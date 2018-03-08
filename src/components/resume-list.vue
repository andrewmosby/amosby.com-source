<template>
	<div class="resumeList">
		<div class="resumeList_section">
			<div class="resume_title">
				<h2>R. Andrew Mosby</h2>
				<p>
					509 Laurel Avenue, Johnson City, TN 37604<br>
					(678) 381 3801 | <a href="mailto:r.andrew.mosby@gmail.com">r.andrew.mosby@gmail.com</a>
				</p>
			</div>
			<a @click="print" class="printHide resumeList_print">Print</a>
			<h3>Employment History</h3>
			<p class="hasOverline">Ntara, Johnson City, TN. June 2013–present.<br>
			<em>Front End Developer:</em> Responsible for the responsive front end development of the creative agency.</p>
			<ul>
				<li>Developed front end of a multitude of responsive sites, ranging from five-page brochure sites to 1000+ page ecommerce and healthcare sites.</li>
				<li>Architected and developed CSS framework for complex designs.</li>
				<li>Worked closely with a team of designers and back end developers to refine user experience and functionality.</li>
				<li>Established a system of Professional Development for other front end developers to keep each of us learning and growing well.</li>
				<li>Created documentation and design guide that can be added to sites as their developed. This documentation also helps onboard developers and CMS users to work on the site.</li>
			</ul>
			<p class="hasOverline">
				Emmanuel Christian Seminary, Johnson City, TN. August 2009–May 2013.<br>
				<em>Graphic Designer and Front End Developer:</em> Responsible for print and web design as well as the front end development of all school-related sites.
			</p>
			<ul>
				<li>Worked together with one co-worker to design and develop a web application ecosystem using CSS, HTML, and javascript.</li>
				<li>Designed a new brand identity for the school. Produced print and web materials based on this branding.</li>
			</ul>
			<p class="hasOverline">Christian Missionary Fellowship, Santiago, Chile. June 2006–July 2009.<br>
				<em>Globalscope Campus Minister</em>
			</p>
			<ul>
				<li>Redesigned the brand and designed all promotional items.</li>
				<li>Directed student leadership groups through encouragement and teaching to greater personal involvement and commitment.</li>
				<li>Spoke Spanish publicly and fluently during weekly events on a variety of subjects.</li>
			</ul>
			<h3>Languages</h3>
			<ul>
				<li>HTML5, CSS3, Javascript</li>
			</ul>

			<h3>Libraries</h3>
			<ul>
				<li>SCSS, .less, jQuery, vue.js</li>
			</ul>
			<h3>Software</h3>
			<ul>
				<li>Visual Studio, VS Code, Adobe Creative Suite, Microsoft Office Suite</li>
			</ul>
			<h3>Education</h3>
			<ul>
				<li>Georgia Institute of Technology, Atlanta, GA. Bachelor of Science in Industrial Design, May 2006.</li>
				<li>Emmanuel Christian Seminary, Johnson City, TN. Master of Arts in Religion, May 2013.</li>
			</ul>
		</div>
	</div>
</template>

<script>

	export default {
		methods: {
			print: function() {
				window.print();
			}
		}
	}
</script>

<style scoped lang="scss">
	@import "./../variables.scss";
	
	.resumeList_section {
		position: relative;

		ul {
			padding-left: 32px;
			list-style-type: disc;
			list-style-position: outside;
		}

		li {
			padding-left: 8px;
		}

		p {
			margin-bottom: 	16px;
		}
	}
	.resumeList_print {
		position: absolute;
		top: -36px;
		right: -36px;
		cursor: pointer;

		@media (max-width: $tabletMax) {
			display: none;
		}
	}
	@media print {
		.resume_title {
			margin-bottom: 24px;

			h2 {
				margin-bottom: 2px;
				font-size: 20px !important;
			}
		}		
		.resumeList_section {
			font-size: 13px;

			a {
				text-decoration: none;
			}
			p {
				margin-bottom: 4px;
			}
			ul {
				margin-bottom: 	16px;
			}
			h3 {
				margin-bottom: 0;
				font-size: 16px !important;
			}
		}
	}
</style>
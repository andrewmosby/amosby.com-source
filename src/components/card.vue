<template>
	<div>
		<div class="projectFilter">
			<div class="projectFilter_label">Filter&nbsp;by:</div>
			<div class="projectFilter_tagWrapper">
				<span @click="filterCards('role', 'all')" class="itemTag">All</span>
				<span @click="filterCards('role', 'Lead Developer')" class="itemTag">Lead Developer</span>
				<span @click="filterCards('role', 'Co-Developer')" class="itemTag">Co-Developer</span>
				<span @click="filterCards('role', 'Mentor')" class="itemTag">Mentor</span>
				<span @click="filterCards('size', 'Major Project')" class="itemTag">Major Project</span>
				<span @click="filterCards('size', 'Minor Project')" class="itemTag">Minor Project</span>
				<span @click="filterCards('tag', 'accessible')" class="itemTag">Accessible</span>
				<span @click="filterCards('tag', 'performanceBudget')" class="itemTag">Performance Budget</span>
				<span @click="filterCards('tag', 'eCommerce')" class="itemTag">eCommerce</span>
				<span @click="filterCards('tag', 'brochure')" class="itemTag">Brochure</span>
				<span @click="filterCards('tag', 'docs')" class="itemTag">Documentation</span>
				<span @click="filterCards('date', '2017')" class="itemTag">2017</span>
				<span @click="filterCards('date', '2016')" class="itemTag">2016</span>
				<span @click="filterCards('date', '2015')" class="itemTag">2015</span>
				<span @click="filterCards('date', '2014')" class="itemTag">2014</span>
				<span @click="filterCards('date', '2013')" class="itemTag">2013</span>
			</div>
		</div>
		<p>Showing <strong>{{ msg }}</strong> items.</p>
		<div class="projectCardList">
			<a v-bind:href="card.url" target="_blank" class="flex_cell projectCard" v-for="card in filteredCards" v-bind:style="{ backgroundImage: 'url(' + card.imgsrc + ')' }">
				<i class="icon-material projectCard_icon">open_in_new</i>
				<div class="projectCard_description">
					<h2 class="projectCard_title">{{ card.title }}</h2>
					{{ card.desc }}
				</div>
				<div class="projectCard_details">
					<div class="itemTag">{{ card.role }}</div>
					<div class="itemTag">{{ card.size }}</div>
					<div class="itemTag">{{ card.tag }}</div>
					<div class="itemTag">{{ card.date }}</div>
				</div>
			</a>
		</div>
	</div>
</template>

<script>
	export default {
		data: function() {
			return {
				search: '',
				//itemColor: 'all',
				cards: [
					{
						url: '//beautyrest.com',
						imgsrc: require('./../assets/beautyrest.jpg'),
						title: 'Beautyrest',
						desc: 'This site has changed a lot since launch in early 2016. Yet, the major challenge remains the same: the main CTA for the site is "Find a Store," as the sales model is fixed in brick-and-mortar stores. The site is responsive with multiple color palette changes based on the product line. The footer is persistent and the CSS and JS animations are sprinkled throughout the site.',
						role: 'Lead Developer',
						size: 'Major Project',
						date: '2016', //March
						tag: 'brochure'
					},
					{
						url: '//www.bosma.org/',
						imgsrc: require('./../assets/bosma.jpg'),
						title: 'Bosma',
						desc: 'We went through great lengths to ensure accessible content for users of bosma.org. Bosma itself both employs and informs BVI (blind and visually impaired) persons, so way beyone 508 or WCAG compliance was expected. We relied on knowledge gained from other accessible site builds to optimize for screen readers and even added keybinds for navigation (press and hold "alt" on the site to see this in action). All of this and one of my favorite facets of this site is still the use of type throughout.',
						role: 'Mentor',
						size: 'Major Project',
						date: '2013', //October
						tag: 'accessible'
					},
					{
						url: '//www.hunterfan.com/casablanca',
						imgsrc: require('./../assets/casablancafanco.jpg'),
						title: 'Casablanca Fan Co',
						desc: 'This project was one of those in which requirements kept changing during development, so keeping up with a consistent code base was a challenge. Yet, the site remains a beautiful testament to the level of design that can be accomplished on a high-end e-commerce site. EDIT: the client has very recently changed agencies and the site is no longer active.',
						role: 'Lead Developer',
						size: 'Major Project',
						date: '2016', //January
						tag: 'eCommerce'
					},
					{
						url: '//www.dimweightsolutions.com/',
						imgsrc: require('./../assets/dimweightsolutions.jpg'),
						title: 'DIM Weight Solutions',
						desc: 'Although this site is a small, informational brocure site, the mobile experience is optimized and the design is simple and clear. Our major accomplishment for this site was the implementation of site documentation for developers and CMS users. Just append "/docs" to the site to see them. Oh, and check out the responsive table in the docs. I am pretty proud of that one :)',
						role: 'Lead Developer',
						size: 'Minor Project',
						date: '2017', //January
						tag: 'docs'
						// Note the docs
					},
					{
						url: '//envisionus.com',
						imgsrc: require('./../assets/envisionus.jpg'),
						title: 'Envision US',
						desc: 'You will note many accessibility features on this site, from alt tags on every image to skippable, tabbable navagation to notifications when the screen will jump. This was our first fully accessible site and we wrote up a nice blog post about the experience, which you can find at codepen.io/team/ntara/posts',
						role: 'Co-Developer',
						size: 'Minor Project',
						date: '2015', //May
						tag: 'accessible'
					},
					{
						url: '//university.envisionus.com/',
						imgsrc: require('./../assets/envisionuniversity.jpg'),
						title: 'Envision University',
						desc: 'A continuing education resource for Envision US, this site utilizes many of the same accessibility features of its sister site. It also features a member login and profile for event attendees and hosts, as well as a cvent reskin for course registration.',
						role: 'Mentor',
						size: 'Minor Project',
						date: '2015', //November
						tag: 'accessible'
					},
					{
						url: '//www.hunterfan.com',
						imgsrc: require('./../assets/hunterfan.jpg'),
						title: 'Hunter Fan',
						desc: 'This site is no longer under my control and does not reflect my code or styles. But, its original design funneled users to fans based on the style, personality, or space of the user.',
						role: 'Lead Developer',
						size: 'Major Project',
						date: '2014', //January
						tag: 'eCommerce'
					},
					{
						url: '//www.hunterindustrialfan.com/',
						imgsrc: require('./../assets/hunterindustrialfan.jpg'),
						title: 'Hunter Industrial Fan',
						desc: "This site aims to inform and generate sales leads for Hunter Fan's line of industrial-size ceiling fans (think Big Ass Fans, their biggest competitor). The mobile experience is optimized and was built modularly with an 'everything first' mindset.",
						role: 'Lead Developer',
						size: 'Minor Project',
						date: '2016', //June
						tag: 'brochure'
					},
					{
						url: '//www.mastgeneralstore.com/',
						imgsrc: require('./../assets/mastgeneralstore.jpg'),
						title: 'Mast General Store',
						desc: "Mast remains one of my favorite projects, as it was my first responsive site, which really set a benchmark for my learning experiences. There are a number of small touches that really cause the site to stand out (note the swatches on product cards and detail pages). It is also unfortunately out of my control today, so I have to sit by and watch 10 slides get loaded to the home page carousel :(",
						role: 'Lead Developer',
						size: 'Major Project',
						date: '2013', //October
						tag: 'eCommerce'
					},
					{
						url: 'https://www.theouterbankshospital.com/',
						imgsrc: require('./../assets/theouterbankshospital.jpg'),
						title: 'Outer Banks Hospital',
						desc: 'This site was special in that it was the first major site build for a newer front end developer on our team. I had provided teaching and encouragement up to this project and it was time for him to make the step to be the lead of a major project. There were definitely some growing pains, but ultimately finished with a good product and confidence for the next project.',
						role: 'Mentor',
						size: 'Major Project',
						date: '2017', //March
						tag: 'brochure'
					},
					{
						url: '//www.teradata.com/',
						imgsrc: require('./../assets/teradata.jpg'),
						title: 'Teradata',
						desc: 'Teradata is a multi-billion dollar corporation involved in database and storage. Their site is the most optimized in my portfolio and features vue.js on a number of pages, including the home page. The CSS is fully componentized and follows a BEM class structure. The team works under an agile methodology.',
						role: 'Lead Developer',
						size: 'Major Project',
						date: '2017', //May
						tag: 'performanceBudget'
					},
					{
						url: '//www.vidanthealth.com',
						imgsrc: require('./../assets/vidanthealth.jpg'),
						title: 'Vidant Health',
						desc: 'Vidant Health is a health care organization in eastern North Carolina for whom we have done multiple site design and builds. This is their main site of over 1700 pages, which includes 20+ templates. A major consideration behind its design and front end architecture is the significant low-fi mobile connections present for its rural clients.',
						role: 'Lead Developer',
						size: 'Major Project',
						date: '2015', //August
						tag: 'brochure'
					},
					// {
					// 	url: '//envisionus.com',
					// 	imgsrc: require('./../assets/desktop-2.jpg'),
					// 	title: 'Vidant Health Cancer Care',
					// 	desc: 'Duis suscipit nibh et libero vestibulum faucibus. Vivamus ullamcorper sodales rhoncus. Maecenas consequat sagittis arcu in aliquam. Interdum et malesuada fames ac ante ipsum primis in faucibus.',
					// 	role: 'Lead Developer',
					// 	size: 'Minor Project',
					// 	date: '2014', //May
					// 	tag: 'brochure'
					// },
					{
						url: '//careers.vidanthealth.com/',
						imgsrc: require('./../assets/vidanthealthcareers.jpg'),
						title: 'Vidant Health Careers',
						desc: 'This site is designed to provide prospective job applicants with information about the company and the area. Most pages are informational, but a major focus of the site is the integration with a third-party job application portal. It was built on an early version of our CSS framework.',
						role: 'Lead Developer',
						size: 'Minor Project',
						date: '2014', //November
						tag: 'brochure'
					},
					{
						url: '//foundation.vidanthealth.com/',
						imgsrc: require('./../assets/vidanthealthfoundation.jpg'),
						title: 'Vidant Health Foundation',
						desc: 'As a non-profit organization, Vidant needed a site to promote its foundation for giving purposes. This site funnels users to major giving campaigns via inspirational content. The front end was built on an early version of our CSS framework.',
						role: 'Mentor',
						size: 'Minor Project',
						date: '2015', //May
						tag: 'brochure'
					}
				],
				filteredCards: [

				],
				msg: "all"
			};
		},
		mounted: function() {
			this.filteredCards = this.cards
		},
		methods: {
			filterCards: function(dataSet, data) {
				this.msg = data
				this.filteredCards = this.cards.filter(function(i) {
					if (data === 'all') {
						return i
					} else if (dataSet === 'size') {
						return i.size === data
					} else if (dataSet === 'role') {
						return i.role === data
					} else if (dataSet === 'date') {
						return i.date === data
					} else if (dataSet === 'tag') {
						return i.tag === data
					}
				})
			}
		}
		// computed: {
		// 	cardList: {
		// 		get: function() {
		// 			console.log("ran filteredItems get function")
		// 			return this.cards
		// 			// return this.cards.filter(function(i) {
		// 			// 	return i.date === '2017'
		// 			// })
		// 		},
		// 		set: function(newValue) {
		// 			console.log("ran filteredItems set function" + " " + newValue)
		// 			this.filteredCards = this.cards.filter(function(i) {
		// 				return i.date === '2017'
		// 			})
		// 		}
		// 	}
		// }
	}
</script>

<style scoped lang="scss">
	@import "../variables.scss";

	.projectFilter {
		display: flex;
		margin-bottom: 75px;
	}

	.projectFilter_label {
		margin: 0 24px 0px 0;
		font-family: $fontPrimary;
		text-transform: uppercase;
		font-weight: 700;
		font-size: 14px;
	}

	$tagSpace: 6px;
	.projectFilter_tagWrapper {
		display: flex;
		flex-wrap: wrap;
		margin-bottom: -$tagSpace; //accounts for margin-bottom on .itemTag
	}

	.itemTag {
		margin-right: $tagSpace;
		margin-bottom: $tagSpace;
		padding: 4px 8px;
		font-size: 14px;
		line-height: 1;
		font-family: $fontPrimary;
		background-color: rgba(255,255,255,.1);
		color: $colorLightGray;
		color: white;
		text-transform: capitalize;
		cursor: pointer;
		transition: $transition;

		&:hover {
			background-color: rgba(255,255,255,.05);
			color: $colorBeige;
		}
	}

	.itemTag-blue {
		background-color: $colorBlue;

		&:hover {
			background-color: darken($colorBlue, 8%);
		}
	}

	.itemTag-yellow {
		background-color: $colorYellow;
		color: $colorBlack;

		&:hover {
			background-color: darken($colorYellow, 2%);
		}
	}

	.itemTag-green {
		background-color: #3ccc68;

		&:hover {
			background-color: darken(#3ccc68, 5%);
		}
	}

	.projectCardList {
		display: grid;
		grid-template-columns: repeat(auto-fit,minmax(320px,1fr));
		grid-gap: 4px;

		@media (max-width: $phoneMax) {
			grid-gap: 24px;
		}
	}

	.projectCard {
		position: relative;
		display: flex;
		align-items: center;
		min-height: 550px;
		padding: 20px;
		background: no-repeat center;
		background-size: cover;
		text-decoration: none;
		color: $colorLightGray;
		flex-direction: column;
		justify-content: space-between;
		transition: $transition;
		filter: saturate(0);

		&:hover {
			transform: scale(1.1);
			box-shadow: 0 0 12px $colorBlack;
			text-decoration: none;
			filter: saturate(1);
			z-index: 1;
		}
		
		@media (min-width: $desktopMin) {
			
			
		}
	}

	.projectCard:before {
		content: "";
		display: block;
		position: absolute;
		top: 0;
		left: 0;
		height: 100%;
		width: 100%;
		background: rgba(0,0,0,0.8);
		z-index: 0;
	}

	.projectCard:hover:before {
		background: fade-out($colorBlack, .8);
	}

	.projectCard_icon {
		position: absolute;
		top: 26px;
		right: 20px;
		z-index: 1;
		font-size: 16px;
		color: white;
	}
	
	.projectCard_description {
		position: relative;
		width: 100%;
		z-index: 1;
		transition: $transition;
	}

	.projectCard:hover {
		.projectCard_description {
			opacity: 0;
		}
		.itemTag {
			background: $colorBlack;
		}

	}

	.projectCard_title {
		margin-bottom: 20px;
		color: $colorBeige;
		padding-right: 24px; //accounts for 'position: absolute;' icon
	}

	.projectCard_date {
		font-family: $fontSecondary;
		font-size: 12px;
		text-transform: uppercase;
	}

	.projectCard_details {
		position: relative;
		display: flex;
		flex-wrap: wrap;
		width: 100%;
		margin-bottom: -$tagSpace; //accounts for margin-bottom on .itemTag		
		align-items: center;
		z-index: 1;
	}

	@media (max-width: $phoneMax) {
		.projectFilter {
			display: block;
		    margin-bottom: 24px;
		}
		.projectFilter_label {
			margin-bottom: 8px;
		}
		.projectCardList {
		    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
		}
	}
</style>
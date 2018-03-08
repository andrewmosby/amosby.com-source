<template>
	<div class="padding">
		<div class="column-small column-centered">
			<h1>About</h1>
			<div class="contentEntry">
				<h2>Code does not define me</h2>
				<h3>The highlights</h3>
				<p>Let's be a little rapid-fire on this. I should start with frisbee. I love ultimate frisbee&mdash;I play the handler position and prefer a free-flowing game to organized stack offenses. I also have fun freestyling with the disc, doing trick throws and catches. Sticking with sports, I'll watch anything with friends, but I only really keep up with soccer these days. I wish I liked it more growing up, but the year I tried playing it, I lived in 100+ degree Texas, so nah. I do play soccer (I lived in Santiago, Chile so I had to learn!), but I'm not great, so it's more for fun.<p>
				</p>That's a good segway into video games. I play a lot of Fifa, but don't peg me for a bro-gamer. I despise shooters (I never had Goldeneye growing up but my friends did and they destroyed me every time) and love RPGs&mdash;J and W for different reasons. Bioware was my favorite game developer until EA bought them and trashed their games.</p>
				<p>For movies and tv, the first that comes to mind is Lord of the Rings. I absolutely love the trilogy, but don't get me started on <em>The Hobbit</em>. The trilogy movies are better than their book counterparts in my opinion, but the (one) <em>Hobbit</em> book is way better than the (three) movies. I grew up quoting <em>Seinfeld</em> and am definitely a better person for it. I love <em>Stranger Things</em> and <em>This is Us</em> (not going out on any limbs there). Randal is just the best.</p>
				<h3>Music</h3>
				<p>What's an 'about' page without a myspace-like curated playlist? Consider it my mixtape to you. Though, if you sent me a mixtape, I'd expect a higher percentage of my boy JT.</p>
				<iframe class="spotifyPlayer" src="https://open.spotify.com/embed/user/1227154210/playlist/4Yl8fiQIF5g1DaSIvSbOep" height="320" frameborder="0" allowtransparency="true"></iframe>
				<p>Speaking of music, I play (more like 'played') the trumpet. In high school, I played 1st trumpet in our Grand National 16th place winning marching band. I bust it out every now and then, but mostly the case is just collecting dust.</p>
				<h3>Miscellaneous</h3>
				<p>Anything else? How about I...</p>
				<ul class="list-bullet">
					<li>speak fluent Spanish</li>
					<li>love a good bourbon</li>
					<li>(but would never pass on tequila)</li>
					<li>definitely say 'yall'</li>
					<li>enjoy snowboarding</li>
					<li>love authentic mexican food</li>
					<li>(but still appreciate the cheesy tex-mex)</li>
					<li>wear the color yellow with pride</li>
					<li>have never actually beaten the original <em>Battletoads</em> game</li>
				</ul>
				<p>Anything more than that and you'll have to <a href="mailto:r.andrew.mosby@gmail.com">email</a> me.</p>
			</div>
		</div>
	</div>
</template>

<script>
	// import cards from './card.vue'

	export default {
		// components: {
		// 	componentCard: cards
		// }
	}
</script>

<style scoped lang="scss">
	@import "./../variables.scss";
	@import "./../mixins.scss";

	.spotifyPlayer {
		width: 100%;
		margin-bottom: $marginTopBottom;
	}

	.list-bullet {
		padding-left: 32px;
		list-style-type: disc;
		list-style-position: outside;

		li {
			padding-left: 8px;
		}
	}
</style>
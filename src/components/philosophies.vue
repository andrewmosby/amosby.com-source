<template>
	<div class="padding">
		<div class="column-small column-centered">
			<h1>Philosophies</h1>
			<div class="contentEntry">
				<h2>Good code and collaboration doesn't just happen</h2>
				<h3>Development</h3>
				<h4>BEM or BEM-like naming</h4>
				<p>Teams need to adopt some sort of standard for class naming and structure. This ensures similar coding practices across sites and allows for other contributors to anticipate and understand without a crash course on the specific code base. <a href="https://en.bem.info/methodology/quick-start/">BEM</a> is by far the most accepted form of front end standards, which makes it the Although, I should say that I prefer a slightly modified version and have been on record as calling BEM &ldquo;<a href="http://www.dimweightsolutions.com/dimweightsolutions/documentation/dimweightsolutions-documentation/methodologies.md.html">fugly</a>.&rdquo;</p>
				
				<h4>Component Markup and CSS</h4>
				<p>From <a href="http://styleguides.io/examples.html">Pattern Libraries</a> to <a href="http://v3.danielmall.com/articles/how-to-make-a-performance-budget/">Performance Budgets</a>, building a site from small components is basically a necessity at this point. You&rsquo;re gaining an organized, structured design and code base and winning in every way with performance. And, when you care just as much about well written markup as you do CSS, ....</p>

				<h4>Fundamentals are more important than specific libraries</h4>
				<p>A beginning front end developer would certainly be forgiven for feeling innundated with information about CSS frameworks like Boostrap and Foundation. Or about JS libraries like Angular, React, and Vue. Not to mention package managers like npm and bower or js task runners like Grunt, Gulp, and Yarn...it can be quite overwhelming! But, I have always said that I care more about a team member&rsquo;s grasp on vanilla CSS and JS rather than their knowledge of one specific library. With strong fundamentals, switching from Bootstrap to Foundation or from React to Vue is doesn&rsquo;t mean starting from scratch.</p>

				<h4>User empathy</h4>
				<p>Front end development used to mean simply cutting up a PSD and translating it for the web. While that does continue to be the base standard for the job, it&rsquo;s so much more than that. But much of the new places to focus attention&mdash;performance, accessibility, testing, the device and browser landscape&mdash;centers around a concern for the user. Being able to ancitpate the needs or sense possible frustrations of the user is an integral characteristic of today&rsquo; front end developer.</p>

				<h4>Simplicity in code</h4>
				<p>Simple code is always preferred to complicated &ldquo;wow factor&rdquo; code. In my experience, over-nested CSS that&rsquo;s reliant on cryptic mixins and JS that requires 200+ dependencies for 10 lines of code require much more time in bug fixes and maintenance costs. In my opinion, a trained dev should be able to walk up and understand code without a crash course on the code base.</p>

				<h4>Expect changes</h4>
				<p>Not only can you expect a site to change post-launch, but 95% of the work I have ever built has been modified mid-build. Some of this can and should be mitigated, but it will always be a reality to some degree. This means that code has to be modular and extensible enough to be modified as it is created. Also, from a team perspective, projects can change hands week-to-week at times, which further reinforces the need for team standards in coding.</p>

				<h3>FED Team</h3>
				<p>The day of the cowboy coder has long passed. And if the above practices are to be followed, a sense of team must be established. Of course this means establishing specifics in those standards and code reviews. More importantly, though, members of the team should know where and how to grow. This involves assessing the strengths of the individual and their desire for areas of continued growth. And, of course this should funnel into the goals of the team and oraganization as a whole.</p>
				<p>This growth can and should come from a director position, but should also come from other senior developers. Other than experience and ability, the biggest differentiator between a senior and a junior developer is that a senior developer can and should teach others for the betterment of the team. This cuts down on juniors making the same mistakes and gives them a model developer to try to emulate.</p>
				
				<h3>Team at-large</h3>
				<p>Collaboration is key. Front end development is truly a bridge position. We have to be able to interpret the intentions of designers while anticipating the needs of back end developers. In my experience, the mindset of those two roles are very different. This leaves us with a very distinct challenge that can make or break a project.</p>
				<p>In a similar way, front end developers can become a key problem solver for clients. Because we are so familiar with the needs of the code base, but we also have an increasing awareness of the needs of the end user, we are in the perfect position to communicate both with the client. As the client perceives difficiencies in the product or prepares for a new campaign for the site, front end developers can help plan for these additions so that the solutions make sense for the site.</p>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		
	}
</script>

<style lang="scss">
	@import "./../variables.scss";
	@import "./../mixins.scss";
</style>
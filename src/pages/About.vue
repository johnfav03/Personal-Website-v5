<template>
	<main class="about">
		<header class="about-header">
			<h1>ABOUT</h1>
		</header>

		<section class="quote">
			<p>
				"Stones in the road? I'll save every single one,
				and one day I'll build a castle."
			</p>
			<span>— Fernando Pessoa</span>
		</section>

		<section class="bio">
			<p>
				I've always been drawn to understanding the stack that makes computing possible: 
                compilers, operating systems, processors, embedded hardware, and everything in between.
                This curiosity led me to my current role as a software engineer on Microsoft's TypeScript Compiler team, 
                where I'm fortunate to work alongside engineers who have shaped modern programming languages, 
                building tools used by millions of developers.
                This work allows me to continue uncovering stones - 
                tricky bugs, unfamiliar systems, problems that push me deeper than expected - 
                and my pile grows with each one. My castle doesn't have a blueprint yet;
                I'm too busy wondering what's under the next stone.
			</p>
		</section>

		<section class="columns">
			<div class="column">
				<h2>Notable Coursework</h2>
				<ul>
					<li>Computer Architecture</li>
					<li>Operating Systems</li>
					<li>Compiler Construction</li>
					<li>Embedded Systems</li>
					<li>Quantum Computing</li>
				</ul>
			</div>

			<div class="column">
				<h2>Outside of Engineering</h2>
				<ul>
					<li>Travel & Hiking</li>
					<li>Cooking & Food</li>
					<li>Volleyball</li>
					<li>Houseplants</li>
					<li>3D Printing</li>
				</ul>
			</div>
		</section>
	</main>
</template>

<style scoped>
.about {
	width: 100%;
	height: 100%;
	padding: clamp(3rem, 15vh, 8rem) clamp(3rem, 15vw, 14rem);
}

.about-header {
	width: 100%;
	margin-bottom: clamp(2rem, 5vh, 4rem);
}

.about-header h1 {
	margin: 0;
	font-size: clamp(2rem, 3vw, 3rem);
	color: var(--acc-thr);
}

.quote {
	width: 100%;
	margin-bottom: clamp(2rem, 5vh, 4rem);
}

.quote p {
	max-width: 60rem;
	margin: 0;
	font-size: clamp(0.9rem, 1.5vw, 1.3rem);
	line-height: 1.5;
	font-style: italic;
	color: #CCC;
}

.quote span {
	display: block;
	margin-top: 0.75rem;
	font-size: 0.9rem;
	padding-left: 2rem;
	color: var(--acc-thr);
}

.bio {
	width: 100%;
	margin-bottom: clamp(3rem, 6vh, 5rem);
}

.bio p {
	max-width: 95ch;
	margin: 0;
	font-size: clamp(0.9rem, 1vw, 1.1rem);
	line-height: 1.5;
	color: #CCC;
}

.columns {
	display: grid;
	grid-template-columns: minmax(0, 0.8fr) minmax(0, 1.2fr);
	gap: clamp(3rem, 8vw, 8rem);
}

.column h2 {
	margin: 0 0 1rem;
	font-size: 0.9rem;
	font-weight: 400;
	color: var(--acc-thr);
}

.column ul {
	list-style: none;
	padding: 0;
	margin: 0;
}

.column li {
	position: relative;
	padding-left: 1.25rem;
	margin: 0.45rem 0;
	font-size: 0.9rem;
	color: #BBB;
	line-height: 1.5;
}

.column li::before {
	content: "";
	position: absolute;
	left: 0;
	top: 0.65rem;
	width: 0.35rem;
	height: 0.35rem;
	border-radius: 50%;
	background: var(--acc-thr);
}
</style>
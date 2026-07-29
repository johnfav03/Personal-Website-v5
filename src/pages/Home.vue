<script setup>
const experiences = [
	{
		role: "Software Engineer",
		type: "Compiler Systems",
		team: "TypeScript Compiler",
		company: "Microsoft",
		date: "Aug 2025 - Present",
		logo: "/logo-microsoft.png"
	},
	{
		role: "Software Engineer Intern",
		type: "Backend & DevOps",
		team: "Platform Infrastructure",
		company: "Tavus",
		date: "May 2024 - Nov 2024",
		logo: "/logo-tavus.png"
	},
	{
		role: "Software Engineer Intern",
		type: "Full Stack",
		team: "Rooftop Consumer",
		company: "EnergySage",
		date: "May 2023 - Aug 2023",
		logo: "/logo-energysage.png"
	},
	{
		role: "Computer Science",
		type: "Electrical Engineering Minor",
		team: "LSA",
		company: "University of Michigan",
		date: "Aug 2021 - May 2025",
		logo: "/logo-umich.png"
	}
]
</script>

<template>
	<div class="home">
		<section class="intro">
			<div class="name-row">
				<h1>JOHN FAVRET</h1>

				<div class="socials">
					<a><
						href="mailto:johnfav@umich.edu"
						target="_blank"
						rel="noopener noreferrer"
						aria-label="Email"
					>
						<img src="/icon-email.png" alt="Email">
					</a>
					<a><
						href="https://www.linkedin.com/in/johnfav"
						target="_blank"
						rel="noopener noreferrer"
						aria-label="LinkedIn"
					>
						<img src="/icon-linkedin.png" alt="LinkedIn">
					</a>
					<a>
						href="https://github.com/johnfav03"
						target="_blank"
						rel="noopener noreferrer"
						aria-label="GitHub"
					>
						<img src="/icon-github.png" alt="GitHub">
					</a>
				</div>
			</div>

			<p class="bio">
				From TypeScript to transistors — always building, occasionally breaking, constantly learning.
				<br>
				<span class="hint">Check the tabs on the right for my work or a bit more about me →</span>
			</p>

			<div class="timeline">
				<div
					v-for="(exp, index) in experiences"
					:key="index"
					class="experience"
				>
					<div class="date">{{ exp.date }}</div>

					<div class="node">
						<div class="logo">
							<img :src="exp.logo" :alt="`${exp.company} logo`">
						</div>
					</div>

					<div class="details">
						<h2>
							{{ exp.company }}
							<span class="separator">·</span>
							<span class="team">{{ exp.team }}</span>
						</h2>

						<p>
							{{ exp.role }}
							<span class="separator">·</span>
							<span class="type">{{ exp.type }}</span>
						</p>
					</div>
				</div>
			</div>
		</section>

		<img src="/bg-flair-orange.png" class="corner-svg" alt="" aria-hidden="true">
	</div>
</template>

<style scoped>
.home {
	width: 100%;
	height: 100%;
	display: flex;
	padding: clamp(3rem, 15vh, 8rem) clamp(3rem, 15vw, 14rem);
	gap: clamp(2rem, 5vw, 5rem);
}

.intro {
	width: 100%;
	z-index: 1;
}

.intro h1 {
	font-size: clamp(2rem, 3vw, 3rem);
	margin-bottom: 0.75rem;
	color: var(--acc-one);
}

.intro .bio {
	width: 100%;
	font-size: clamp(0.9rem, 1vw, 1.1rem);
	line-height: 1.5;
	margin-bottom: clamp(2rem, 4vh, 3rem);
	color: #CCC;
}

.hint {
	font-size: clamp(0.9rem, 1vw, 1.1rem);
	line-height: 2;
	color: #777;
}

.timeline {
	position: relative;
}

.timeline::before {
	content: "";
	position: absolute;
	left: 9.9rem;
	top: 0;
	bottom: 0;
	width: 0.1875rem;
	background: var(--acc-one);
}

.timeline::after {
	content: "";
	position: absolute;
	left: 158px;
	bottom: 0px;
	width: 3px;
	height: 3px;
	background: var(--acc-one);
	box-shadow:
		0 8px 0 var(--acc-one),
		0 16px 0 var(--acc-one);
}

.experience {
	display: grid;
	grid-template-columns: 8.75rem 2.5rem 1fr;
	align-items: start;
	margin-bottom: 2.5rem;
}

.date {
	text-align: right;
	padding-right: 1.25rem;
	padding-top: 0.45rem;
	font-size: 0.75rem;
	color: #777;
}

.node {
	position: relative;
}

.logo {
	width: 2.5rem;
	height: 2.5rem;
	border-radius: 0.25rem;
	border: 0.1875rem solid var(--acc-one);
	background: var(--bg-dark);
	position: relative;
	z-index: 1;
}

.logo img {
	width: 100%;
	height: 100%;
	object-fit: contain;
	padding: 4px;
}

.details {
	padding-left: 1.25rem;
}

.details h2 {
	margin: 0.25rem 0;
	font-size: 1.1rem;
	font-weight: 300;
	line-height: 1.8rem;
}

.details p {
	margin: 4px 0;
	font-size: 0.9rem;
	color: #BBB;
}

.separator {
	margin: 0 5px;
	color: #777;
	font-weight: 300;
}

.team {
	font-size: 1rem;
	color: #777;
	font-weight: 300;
	padding-left: 0.2rem;
}

.type {
	font-size: 0.9rem;
	color: #777;
	font-weight: 300;
	padding-left: 0.2rem;
}

.corner-svg {
	position: absolute;
	bottom: 0px;
	right: 40px;
	width: 50vw;
	height: auto;
	z-index: 0;
	opacity: 1;
	pointer-events: none;
	user-select: none;
}

.name-row {
	display: flex;
	align-items: center;
	gap: 1rem;
}

.name-row h1 {
	margin-bottom: 0.75rem;
}

.socials {
	display: flex;
	align-items: center;
	gap: 0.8rem;
	margin-bottom: 0.75rem;
	margin-left: 1.5rem;
}

.socials a {
	display: flex;
	align-items: center;
	justify-content: center;
	height: 1.25rem;
	transition: transform 0.2s ease;
}

.socials img {
	width: 100%;
	height: 100%;
	object-fit: contain;
	opacity: 0.6;
	transition:
		opacity 0.2s ease,
		transform 0.2s ease;
}

.socials a:hover img {
	opacity: 1;
	transform: translateY(-2px);
}
</style>
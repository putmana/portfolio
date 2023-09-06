<script>
	import { fly } from "svelte/transition"
	import BannerCard from "$lib/components/cards/banner-card.svelte"
	import ProjectCard from "$lib/components/cards/project-card.svelte"

	let animTime = 0.4
</script>

<svelte:head>
	<title>Projects | Adam Putman</title>
</svelte:head>

<div class="content" transition:fly={{ y: 50, duration: 500 }}>
	<div class="row" style="--offset-time: {1 * animTime}s">
		<BannerCard>My Projects</BannerCard>
	</div>
	<div class="row" style="--offset-time: {2 * animTime}s">
		<ProjectCard
			header="Marigold"
			image="/images/marigold_scaled.jpg"
			alt="Screenshot of Marigold"
			buttonLink="https://marigoldmusic.live/auth/login"
			buttonLabel="Check it out"
			tag="Full Stack"
		>
			<p>
				A demo of a full-stack desktop music streaming app I built as my college capstone project.
				The idea is to allow users to upload their own music tracks and play them back from here,
				providing the convenience of music streaming with the control of an MP3 player.
			</p>
			<p>Built with <b>SvelteKit, SCSS, TypeScript, Laravel, and MySQL</b></p>
		</ProjectCard>
	</div>
	<div class="row" style="--offset-time: {3 * animTime}s">
		<ProjectCard
			header="Skygaze"
			image="/images/stargaze_scaled.png"
			alt="Screenshot of Stargaze"
			tag="Fully Responsive"
			buttonLink={"https://skygaze.ptmn.io"}
			buttonLabel="Check it out"
			reversed
		>
			<p>
				A fully responsive weather app with a unique pixel art style designed and built entirely by
				me. I even made the icons. Uses the OpenWeatherMap API to find the weather near you. Built
				to be a fun project to put on my portfolio.
			</p>
			<p>Built with <b>SvelteKit, SCSS, and TypeScript</b></p>
		</ProjectCard>
	</div>
	<div class="row" style="--offset-time: {4 * animTime}s">
		<ProjectCard
			header="B-Sides"
			image="/images/bsides_scaled.jpg"
			alt="Screenshot of B-Sides"
			tag="Full Stack & Fully Responsive"
			buttonLink={"https://bsides.ptmn.io"}
			buttonLabel="Check it out"
		>
			<p>
				A simple responsive board-based image forum website. This was originally a college project I
				built during my freshman year, but I've made some major modifications under the hood to make
				it more modular.
			</p>
			<p>Built with <b>Flask, Bootstrap, and MySQL</b></p>
		</ProjectCard>
	</div>
	<div class="row" style="--offset-time: {5 * animTime}s">
		<ProjectCard
			header="RentAssist"
			image="/images/coming-soon.png"
			alt="Coming soon"
			tag="Full Stack & Fully Responsive"
			buttonLink={"https://rentassist.ptmn.io"}
			buttonLabel="Coming Soon"
			reversed
			disabled
		>
			<p>
				A website to help roomates split rent and other expenses. Initially built as an extremely
				simple calculator to help me split my rent with my roomates, I saw an opportunity to turn
				this into a real project.
			</p>
			<p>Built with <b>Vue, Bootstrap, TypeScript, and PocketBase</b></p>
		</ProjectCard>
	</div>
	<div class="row" style="--offset-time: {6 * animTime}s">
		<ProjectCard
			header="Grocery List"
			image="/images/grocery-list_scaled.png"
			alt="Screenshot of grocery list website"
			tag="Fully Responsive"
			buttonLink={"https://demo.ptmn.io/grocery-list"}
			buttonLabel="Check it out"
		>
			<p>
				The obligatory checklist app. You can add and remove items, change their order, and mark
				them as important. I built this a long time ago, but I'm still pretty happy with how the
				styling turned out.
			</p>
			<p>Built with <b>Vue and Bootstrap</b></p>
		</ProjectCard>
	</div>
</div>

<style lang="scss">
	@use "/src/lib/style/lib.scss";
	@keyframes hold {
		0% {
			opacity: 0%;
			transform: translateY(50px);
		}
		100% {
			opacity: 0%;
			transform: translateY(50px);
		}
	}

	@keyframes slideAndFade {
		0% {
			transform: translateY(50px);
			opacity: 0%;
		}
		100% {
			transform: translateY(0%);
			opacity: 100%;
		}
	}

	.row {
		display: flex;
		flex-wrap: wrap;
		flex-direction: row;
		animation:
			var(--offset-time) ease-in-out 0s 1 hold,
			0.5s ease-in-out var(--offset-time) 1 slideAndFade;
		@media (max-width: lib.$xlarge) {
			flex-direction: column;
		}
	}
</style>

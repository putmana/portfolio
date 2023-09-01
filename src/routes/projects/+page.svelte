<script>
    import { fly } from "svelte/transition";
    import BannerCard from "$lib/components/cards/banner-card.svelte";
    import ProjectCard from "$lib/components/cards/project-card.svelte";

    let animTime = 0.4;
</script>

<svelte:head>
    <title>Projects | Adam Putman</title>
</svelte:head>

<div class="content" transition:fly={{y: 50, duration: 500}}>
    <div class="row" style="--offset-time: {1 * animTime}s">
        <BannerCard>
            My Projects
        </BannerCard>
    </div>
    <div class="row" style="--offset-time: {2 * animTime}s">
        <ProjectCard header="Marigold" image="/images/marigold.png" alt="Screenshot of Marigold" buttonLink="https://marigoldmusic.live/auth/login" buttonLabel="Check out the demo" tag="Full Stack">
            <p>A demo of a full-stack desktop music streaming app I built as my college capstone project. The idea is to allow users to upload their own music tracks and play them back from here, providing the convenience of music streaming with the control of an MP3 player.</p>
            <p>Built with <b>SvelteKit, SCSS, TypeScript, Laravel, and MySQL</b></p>
        </ProjectCard>
    </div>
    <div class="row" style="--offset-time: {3 * animTime}s">
        <ProjectCard header="Skygaze" image="/images/stargaze.png" alt="Coming soon" tag="Fully Responsive" buttonLink={"https://stargaze.ptmn.io"} buttonLabel="Check it out" reversed>
            <p>A fully responsive weather app with a unique pixel art style designed and built entirely by me. I even made the icons. Uses the OpenWeatherMap API to find the weather near you. Built to be a fun project to put on my portfolio.</p>
            <p>Built with <b>SvelteKit, SCSS, and TypeScript</b></p>
        </ProjectCard>
    </div>
    <div class="row" style="--offset-time: {4 * animTime}s">
        <ProjectCard header="RentAssist" image="/images/coming-soon.png" alt="Coming soon" tag="Full Stack & Fully Responsive" buttonLink={"https://rentassist.ptmn.io"} buttonLabel="Coming Soon" disabled>
            <p>A website to help roomates split rent and other expenses. Initially built as an extremely simple calculator to help me split my rent with my roomates, I saw an opportunity to turn this into a real project.</p>
            <p>Built with <b>Svelte, Bootstrap, TypeScript, and PocketBase</b></p>
        </ProjectCard>
    </div>
    <div class="row" style="--offset-time: {5 * animTime}s">
        <ProjectCard header="Store Page" tag="College Project" buttonLink={"https://demo.ptmn.io/store-page"} buttonLabel="Check out the demo">
            <p>A responsive demo of a store page I built in college. Features a review section, different product variants, and an "add to cart" feature.</p>
            <p>Built with <b>Vue and Bootstrap</b></p>
        </ProjectCard>
        <ProjectCard header="Grocery List" tag="College Project" buttonLink={"https://demo.ptmn.io/grocery-list"} buttonLabel="Check out the demo">
            <p>A demo of a responsive checklist app. You can add and remove items, change their order, and mark them as important.</p>
            <p>Built with <b>Vue and Bootstrap</b></p>
        </ProjectCard>
    </div>
    

    
</div>

<style lang="scss">
    @use '/src/lib/style/lib.scss';
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
        animation: var(--offset-time) ease-in-out 0s 1 hold, 0.5s ease-in-out var(--offset-time) 1 slideAndFade;
        @media (max-width: lib.$xlarge) {
            flex-direction: column;
        }
    }
</style>
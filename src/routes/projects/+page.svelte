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
            Projects
        </BannerCard>
    </div>
    <div class="row" style="--offset-time: {2 * animTime}s">
        <ProjectCard header="Marigold" image="/images/marigold.png" alt="Screenshot of Marigold" buttonLink="https://marigoldmusic.live/auth/login" buttonLabel="Check out the demo" tag="Under Construction">
            <p>A full-stack music streaming app that puts you in the driver's seat. Upload your own music and enjoy the convenience of streaming apps while retaining control of your library. By far the coolest thing I've built (yet...)</p>
            <p>Built with <b>SvelteKit, SCSS, TypeScript, Laravel, and MySQL</b></p>
        </ProjectCard>
    </div>
    <div class="row" style="--offset-time: {3 * animTime}s">
        <ProjectCard header="Stargaze" image="/images/stargaze.png" alt="Coming soon" tag="Coming Soon" buttonLink={"https://rentassist.ptmn.io"} buttonLabel="Coming Soon" reversed disabled>
            <p>A fully responsive weather app with a unique pixel art style. Uses your location and the OpenWeatherMap API to find the weather near you. All icons and backgrounds were created by me.</p>
            <p>Built with <b>SvelteKit, SCSS, and TypeScript</b></p>
        </ProjectCard>
    </div>
    <div class="row" style="--offset-time: {4 * animTime}s">
        <ProjectCard header="RentAssist" image="/images/coming-soon.png" alt="Coming soon" tag="Coming Soon" buttonLink={"https://rentassist.ptmn.io"} buttonLabel="Coming Soon" disabled>
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
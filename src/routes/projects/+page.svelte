<script>
    import { fly } from "svelte/transition";
    import BannerCard from "$lib/components/cards/banner-card.svelte";
    import ProjectCard from "$lib/components/cards/project-card.svelte";

    let animTime = 0.4;

</script>
<div class="content" transition:fly={{y: 50, duration: 500}}>
    <div class="row" style="--offset-time: {1 * animTime}s">
        <BannerCard>
            Projects
        </BannerCard>
    </div>
    <div class="row" style="--offset-time: {2 * animTime}s">
        <ProjectCard header="Marigold" image="/images/marigold.png" alt="Screenshot of Marigold" buttonLink="https://marigoldmusic.live" buttonLabel="Check out the demo" tag="Under Construction">
            <p>A full-stack music streaming app that puts you in the driver's seat. Upload your own music and enjoy the convenience of streaming apps while retaining control of your library. By far the coolest thing I've built (yet...)</p>
            <p>Built with <b>SvelteKit, SCSS, TypeScript, Laravel, and MySQL</b></p>
        </ProjectCard>
    </div>
    <div class="row" style="--offset-time: {3 * animTime}s">
        <ProjectCard header="My Old Website" image="/images/old-website.jpeg" alt="Screenshot of old website" buttonLink="https://marigoldmusic.live" buttonLabel="Check it out" reversed>
            <p>An older version of my portfolio website I built in college.</p>
            <p>Built with <b>Bootstrap and jQuery</b></p>
        </ProjectCard>
    </div>
    <div class="row" style="--offset-time: {4 * animTime}s">
        <ProjectCard header="Stargaze" image="/images/coming-soon.png" alt="Coming soon" tag="Coming Soon">
            <p>An API-based weather app with a beautiful pixel art style.</p>
            <p>Built with <b>SvelteKit, SCSS, and TypeScript</b></p>
        </ProjectCard>
    </div>
    <div class="row" style="--offset-time: {5 * animTime}s">
        <ProjectCard header="RentAssist" image="/images/coming-soon.png" alt="Coming soon" tag="Coming Soon" reversed>
            <p>A simple application to help roomates split rent and other expenses on a monthly basis.</p>
            <p>Built with <b>Svelte, Bootstrap, TypeScript, and PocketBase</b></p>
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
        animation: var(--offset-time) ease-in-out 0s 1 hold, 0.5s ease-in-out var(--offset-time) 1 slideAndFade;
    }
</style>
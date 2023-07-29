<script>
    import BannerCard from "$lib/components/cards/banner-card.svelte";
    import ProjectCard from "$lib/components/cards/project-card.svelte";

</script>
<div class="content">
    <div class="row">
        <BannerCard>
            Projects
        </BannerCard>
    </div>
    <div class="row">
        <ProjectCard hue="30" header="Marigold" image="/images/marigold.png" alt="Screenshot of Marigold" buttonLink="https://marigoldmusic.live" buttonLabel="Check out the demo">
            <p>A full-stack music streaming app that puts you in the driver's seat. Upload your own music and enjoy the convenience of streaming apps while retaining control of your library. By far the coolest thing I've built (yet...)</p>
            <p>Built with <b>SvelteKit, SCSS, TypeScript, Laravel, and MySQL</b></p>
        </ProjectCard>
    </div>
    <div class="row">
        <ProjectCard hue="30" header="My Old Website" image="/images/old-website.jpeg" alt="Screenshot of old website" buttonLink="https://marigoldmusic.live" buttonLabel="Check out the demo" reversed>
            <p>An older version of my portfolio website I built in college.</p>
            <p>Built with <b>Bootstrap and jQuery</b></p>
        </ProjectCard>
    </div>
    

    
</div>

<style lang="scss">
    @use '/src/lib/style/lib.scss';

</style>
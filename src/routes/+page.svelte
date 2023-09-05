<script>
    import { fly } from "svelte/transition";

    import BannerCard from "$lib/components/cards/banner-card.svelte";
    import HeroCard from "$lib/components/cards/hero-card.svelte";
    import ImageCard from "$lib/components/cards/image-card.svelte";
    import InfoCard from "$lib/components/cards/info-card.svelte";

    let animTime = 0.4;

</script>

<svelte:head>
    <title>Home | Adam Putman</title>
</svelte:head>

<div class="content" transition:fly={{y: 50, duration: 500}}>
    <div class="row" style="--offset-time: {1 * animTime}s">
        <HeroCard header="Hi, I'm Adam." image="/images/hero-bg-code-dark.png" buttonLink="/projects" buttonLabel="See My Work">
            Aspiring front-end web developer
        </HeroCard>
    </div>
    <div class="row" style="--offset-time: {2 * animTime}s">
        <InfoCard header="About Me">
            <p>Full-stack web developer based in Billings, Montana.</p>
            <p>Graduated in 2023 from Montana State University Billings with an Associates Degree in Computer Programming and Application Development</p>
            <p>Mainly specialized in front-end development (HTML, CSS, JavaScript, Svelte, Vue, Bootstrap, SCSS, and TypeScript)</p>
            <p>Also experienced in back-end development (PHP, Laravel, Python, and MySQL)</p>
            <p>Sharp eye for design</p>
            <p>Knows Linux</p>
            <p>Owns a cockatiel</p>
        </InfoCard>
        <ImageCard image="/images/portrait.jpg" caption="Red Lodge, Montana" />
    </div>
</div>
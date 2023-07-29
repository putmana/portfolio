<script>
    import BannerCard from "$lib/components/cards/banner-card.svelte";
import HeroCard from "$lib/components/cards/hero-card.svelte";
    import ImageCard from "$lib/components/cards/image-card.svelte";
    import InfoCard from "$lib/components/cards/info-card.svelte";

</script>
<svelte:head>
    <title>About | Adam Putman</title>
</svelte:head>

<div class="content">
    <div class="row">
        <HeroCard header="Hi, I'm Adam." image="/images/hero-bg-code-dark.png" buttonLink="/projects" buttonLabel="See My Work">
            Full-stack web designer/developer
        </HeroCard>
    </div>
    <div class="row">
        <InfoCard header="About Me">
            <p>Full-stack web developer based in Billings, Montana.</p>
            <p>Graduated in 2023 from Montana State University Billings with an Associates Degree in Computer Programming and Application Development</p>
            <p>Mainly specialized in front-end development (HTML, CSS, JavaScript, Svelte, Vue, Bootstrap, SCSS, and TypeScript)</p>
            <p>Also experienced in back-end development (Node, PHP, Laravel, Python, and MySQL)</p>
            <p>Sharp eye for design</p>
            <p>Extremely comfortable with Linux</p>
            <p>Owns a cockatiel</p>
        </InfoCard>
        <ImageCard image="/images/hero-bg-color-sm.jpg" caption="Red Lodge, Montana" />
    </div>
</div>

<!---
<div class="content">

    <InfoCard header="Hi, I'm Adam" buttonLink="/projects" buttonLabel="See my work" size=4>
        <p>I'm a full-stack web developer based in Billings, Montana.</p>
        <p>I have a wide range of experience with several front-end languages and frameworks, such as Svelte, Vue, jQuery, Bootstrap, and SCSS.</p>
        <p>I also have experience with back-end technologies like PHP, Laravel, Flask, Django, Node, and SQL.</p>
        <p>With a keen eye for design, I know how to make your website beautiful and functional at the same time.</p>
    </InfoCard>

    <section class="hero">
        <div class="caption">
            Red Lodge, Montana
        </div>
    </section>

</div>
--->

<style lang="scss">
    @use '/src/lib/style/lib.scss';

    
    
</style>
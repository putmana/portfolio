<script>
    import InfoCard from "$lib/components/cards/info-card.svelte";

</script>
<svelte:head>
    <title>About | Adam Putman</title>
</svelte:head>
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


<style lang="scss">
    @use '/src/lib/style/lib.scss';

    .content {
        margin: 60px;
        margin-top: 30px;
        display: flex;
        flex-wrap: wrap;
        flex-direction: row;
        justify-content: center;

        @media (max-width: lib.$xlarge) {
            flex-direction: column;
        }

        @media (max-width: lib.$large) {
            margin: 15px;
            margin-top: 0px;
        }
        
    }

    .hero {
        display: flex;
        flex-direction: column-reverse;
        min-height: 300px;
        background-image: url("/images/hero-bg-color.jpg");
        background-size: cover;
        margin: 10px;
        flex: 3;
        background-position: center;
        background-color: lib.$color-bg-c;
        border: 3px solid lib.$color-accent-a;
        box-shadow: 8px 8px 0px lib.$color-accent-a;

        .caption {
            padding: 10px;
            background-color: lib.$color-bg-b;
            border-top: 3px solid lib.$color-accent-a;
        }
    }
    
</style>
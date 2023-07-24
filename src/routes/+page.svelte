<script>

</script>
<div class="wrapper">
    <section class="namecard">
        <div class="name">
            Hi, I'm <span class="emphasis">Adam</span>

        </div>
        <div class="subtext">
            I'm a full-stack web developer based in Billings, Montana.
        </div>
        <div class="subtext">
           I have a wide range of experience with several front-end languages and frameworks, such as Svelte, Vue, jQuery, Bootstrap, and SCSS.
        </div>
        <div class="subtext">
            I also have experience with back-end technologies like PHP, Laravel, Flask, Django, Node, and SQL.
        </div>
        <div class="subtext">
            With a keen eye for design, I know how to make your website beautiful and functional at the same time.  
        </div>
        <div class="btn">
            <button class="btn-primary bigger on-card">
                See my work
            </button>
        </div>
        
    </section>
    <section class="hero">
        <div class="caption">
            Red Lodge, Montana
        </div>
    </section>

</div>


<style lang="scss">
    @use '/src/lib/style/lib.scss';

    .wrapper {
        margin: 60px;
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

    .namecard {
        margin: 10px;
        flex: 4;
        padding: 60px;
        color: lib.$color-accent-a;
        background-color: lib.$color-bg-b;
        border: 3px solid lib.$color-accent-a;
        box-shadow: 8px 8px 0px lib.$color-accent-a;
        .name {
            font-size: 60pt;
            font-weight: 400;
            letter-spacing: -8px;
        }
        .subtext {
            margin-top: 20px;
            margin-left: 7px;
            padding-left: 30px;
            font-size: 14pt;
            font-weight: 500;

            border-left: 6px solid lib.$color-accent-a;
        }
        .emphasis {
            font-weight: 500;
            color: lib.$color-accent-a;
        }
        .btn {
            display: flex;
            margin-top: 40px;
        }
        
        @media (max-width: lib.$large) {
            padding: 30px;
            .name {
                font-size: 30pt;
                letter-spacing: -2px;
            }
            .subtext {
                font-size: 12pt;

            }
            .btn {
                justify-content: center;
            }
        }

        
    }

    .hero {
        display: flex;
        flex-direction: column-reverse;
        min-height: 300px;
        background-image: url("/images/hero-bg.jpg");
        background-size: cover;
        margin: 10px;
        flex: 3;
        background-position: center;
        background-color: lib.$color-primary-c;
        border: 3px solid lib.$color-accent-a;
        box-shadow: 8px 8px 0px lib.$color-accent-a;

        .caption {
            padding: 10px;
            background-color: lib.$color-bg-b;
            border-top: 3px solid lib.$color-accent-a;
        }
    }
    
</style>
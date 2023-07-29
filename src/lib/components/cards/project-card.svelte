<script lang=ts>
    export let header: string;
    export let hue: string = "151";
    export let image: string = "";
    export let buttonLink: string | null = null;
    export let buttonLabel: string | null = null;
    export let reversed: boolean = false;
    export let alt: string = "";

</script>

<div class="card" style="--hue: {hue}" class:reversed>
    <div class="info">
        <div class="header">
            {header}
        </div>
        <div class="body">
            <slot/>
        </div>
        {#if buttonLink !== null && buttonLabel !== null}
            <div class="footer">
                <a class="btn-primary" href={buttonLink}>
                    {buttonLabel}
                </a>
            </div>
        {/if}
    </div>
    <div class="image">
        <img src={image} alt={alt}>
    </div>
    
</div>

<style lang="scss">
    @use '/src/lib/style/lib.scss';
    .card {
        display: flex;
        flex-direction: row;
        color: lib.$color-accent-a;
        border-color: lib.$color-accent-a;
        background-color: lib.$color-bg-b;
        padding: 60px;
        .info {
            flex: 2;
            display: flex;
            flex-direction: column;
            .header {
                display: flex;
                font-size: 30pt;
                font-weight: 600;
                letter-spacing: -1px;
            }
            .body {
                display: flex;
                flex-direction: column;
                margin-top: 20px;
                margin-left: 8px;
                padding-left: 30px;
                font-size: 14pt;
                font-weight: 500;
                border-left: 3px dotted hsl(var(--hue), lib.$sat-accent, lib.$lig-accent-a);
            }
            .footer {
                display: flex;
                margin-top: 40px;
                margin-left: 6px;
            }
        }
        .image {
            padding-left: 60px;
            display: flex;
            flex: 3;
     
            img {
                box-shadow: 8px 8px 0px lib.$color-bg-c;
                max-width: 100%;
                max-height: 100%;
                object-fit: cover;
                object-position: left;
            }
        }
        &.reversed {
            flex-direction: row-reverse;
            .image {
                padding-left: 0px;
                padding-right: 60px;
            }
        }
    }
    @media (max-width: lib.$xlarge) {
        .card {
            flex-direction: column-reverse;
            
            .image {
                padding-left: 0px;
                padding-bottom: 30px;
            }

            &.reversed {
                flex-direction: column-reverse;
                .image {
                    padding-right: 0px;
                }
            }
            
        }
    }
    @media (max-width: lib.$large) {
        .card {
            padding: 0px;
            .info {
                padding: 30px;
                .header {
                    font-size: 20pt;
                    justify-content: center;
                }
                .body {
                    font-size: 12pt;
                    margin-left: 0px;
                }
                .footer {
                    justify-content: center;
                }
            }
            .image {
                padding-bottom: 0px;
                border-bottom: 3px solid lib.$color-accent-a;
                img {
                    box-shadow: none;
                }
            }
        }
    }
</style>
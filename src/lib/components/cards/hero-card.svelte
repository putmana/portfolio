<script lang=ts>
    export let header: string;
    export let image: string = "";
    export let buttonLink: string | null = null;
    export let buttonLabel: string | null = null;
</script>

<div class="card" style="--hero-img: url({image})">
    <div class="info">
        <div class="header">
            {header}
        </div>
        <div class="body">
            <slot/>
        </div>
        {#if buttonLink !== null && buttonLabel !== null}
            <div class="footer">
                <a class="btn-primary bigger" href={buttonLink}>
                    {buttonLabel}
                </a>
            </div>
        {/if}
    </div>
    
</div>

<style lang="scss">
    @use '/src/lib/style/lib.scss';
    .card {
        display: flex;
        flex-grow: 1;
        height: 100%;
        flex-direction: row;
        align-items: center;
        color: lib.$color-bg-a;
        padding-top: 160px;
        padding-bottom: 160px;
        background-image: var(--hero-img);
        background-size: cover;
        background-position: center;
        background-attachment: fixed;
        
        .info {
            display: flex;
            flex-grow: 1;
            flex-direction: column;
            align-items: center;
            text-align: center;
            .header {
                font-size: 72pt;
                font-weight: 600;
                letter-spacing: -6px;
            }
            .body {
                font-size: 16pt;
                margin: 20px;
            }
            .footer {
                margin-top: 10px;
            }
        }
    }
    @media (max-width: lib.$large) {
            .card {
                .info {
                    .header {
                        font-size: 36pt;
                        letter-spacing: -2px;
                    }
                }
            }
        }
</style>
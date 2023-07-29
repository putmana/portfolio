<script lang="ts">
    let hidden = true;
</script>

<div class="container">
    <div class="toggle-bar" class:hidden>
        <a class="logo" href="/">
            PTMN<span class="accent">.</span>
        </a>
        <input type="checkbox" id="toggle" class="toggler-box" bind:checked={hidden}>
        <label class="toggler" class:hidden for="toggle"><i class="bi bi-list"></i></label>
    </div>
    <ul class="links" class:hidden>
        <a class="link" href="/">
            HOME
        </a>
        <a class="link" href="/projects">
            PROJECTS
        </a>
        <a class="link" href="/contact">
            CONTACT
        </a>
    </ul>
</div>


<style lang="scss">
    @use '/src/lib/style/lib.scss';
    .accent {
        color: lib.$color-accent-c;
    }


    .container {
        display: flex;
        background-color: lib.$color-bg-a;
    }
    .toggle-bar {
        display: flex;
        align-items: center;
        padding-left: 30px;
        padding-right: 30px;
        .logo {
            transition: all 0.2s ease;
            color: lib.$color-accent-a;
            text-decoration: none;
            font-size: 14pt;
            font-weight: 800;
            &:hover {
                color: lib.$color-accent-a;
                box-shadow: 0px 5px 0px lib.$color-accent-a;
            }
            &:active {
                color: lib.$color-bg-c;
                box-shadow: 0px 5px 0px lib.$color-bg-c;
            }
            &:focus-visible {
                outline: 3px dotted lib.$color-accent-a;
            }
        }
        .toggler-box {
            display: none;
        }
        .toggler {
            padding: 6px;
            color: lib.$color-bg-a;
            background-color: lib.$color-accent-c;
            box-shadow: 4px 4px 0px lib.$color-accent-a;
            transition: all 0.2s ease;
            &:hover:active {
                color: lib.$color-bg-b;
                background-color: lib.$color-accent-b;
            }
            &.hidden {
                color: lib.$color-accent-a;
                background-color: transparent;
                box-shadow: none;

                &:hover:active {
                    color: lib.$color-bg-b;
                    background-color: lib.$color-accent-b;
                }
            }
            
        }
    
    }
    .links {
        margin: 0;
        padding-left: 30px;
        display: flex;
        list-style-type: none;
        flex-grow: 1;
        padding-right: 30px;
    }
    .link {
        color: inherit;
        text-decoration: none;
        transition: all 0.2s ease;
        padding: 10px;
        font-weight: 600;

        &:hover {
            color: lib.$color-accent-a;
            box-shadow: 0px 5px 0px lib.$color-accent-a;
        }
        &:active {
            color: lib.$color-bg-c;
            box-shadow: 0px 5px 0px lib.$color-bg-c;
        }
        &:focus-visible {
            outline: 3px dotted lib.$color-accent-a;
        }
    }
    @media (max-width: calc(lib.$large - 1px)) {
        .toggle-bar {
            padding-top: 20px;
            padding-bottom: 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        .container {
            flex-direction: column;
            min-height: 70px;
            
        }
        .links {
            position: relative;
            top: 0px;
            max-width: fit-content;
            flex-direction: column;
            padding-bottom: 180px;
            transition: all 0.3s ease;
            height: 0;
            &.hidden {
                padding-bottom: 0px;
                top: -200px;
                opacity: 0;
            }
        }
        .link {
            margin-top: 10px;
        }
        
    }
    @media (min-width: lib.$large) {
        .container {
            height: 70px;
            align-items: center;
        }
        .toggle-bar {
            flex-grow: 1;
            .logo {
                line-height: 20px;
            }
            .toggler {
                visibility: hidden;
            }
            
        }
        .links {
            flex-direction: row;
            flex-grow: 0;
            .link {
                margin-left: 5px;
            }
        }   
    }

</style>
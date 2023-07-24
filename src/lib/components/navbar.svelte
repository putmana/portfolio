<script lang="ts">
    let hidden = true;

    
</script>

<div class="container">
    <div class="toggle-bar" class:hidden>
        <div class="logo">
            PTMN<span class="accent">.</span>

        </div>
        <input type="checkbox" id="toggle" class="toggler-box" bind:checked={hidden}>
        <label class="toggler" class:hidden for="toggle"><i class="bi bi-list"></i></label>
    </div>
    <ul class="links" class:hidden>
        <a class="link" href="#">
            CONTACT
        </a>
        <a class="link" href="#">
            PROJECTS
        </a>
        <a class="link" href="#">
            ABOUT
        </a>
    </ul>
</div>


<style lang="scss">
    @use '/src/lib/style/lib.scss';
    .accent {
        color: lib.$color-primary-b;
    }


    .container {
        display: flex;
        padding-left: 30px;
        padding-right: 30px;
    }
    .toggle-bar {
        display: flex;
        align-items: center;
        .logo {
            font-size: 14pt;
            font-weight: 800;
        }
        .toggler-box {
            display: none;
        }
        .toggler {
            padding: 4px;
            color: lib.$color-accent-a;
            background-color: lib.$color-primary-c;
            border: 2px solid lib.$color-accent-a;
            transition: all 0.2s ease;
            &:hover:active {
                color: lib.$color-accent-a;
                background-color: lib.$color-primary-c;
                border: 2px solid lib.$color-accent-a;
                box-shadow: 4px 4px 0px lib.$color-accent-a;
            }
            &.hidden {
                color: lib.$color-accent-a;
                background-color: transparent;
                border: 2px solid transparent;
                &:hover:active {
                    border: 2px solid lib.$color-accent-a;
                }
            }
            
        }
    
    }
    .links {
        padding: 0;
        margin: 0;
        display: flex;
        list-style-type: none;
    }
    .link {
        color: inherit;
        text-decoration: none;
        transition: all 0.2s ease;
        padding: 10px;

        &:hover {
            color: lib.$color-accent-a;
            box-shadow: 0px 5px 0px lib.$color-accent-a;
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
            flex-direction: row-reverse;
            
            .link {
                margin-left: 5px;
            }
        }   
    }

</style>
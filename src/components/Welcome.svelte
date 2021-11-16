<script lang="ts">
    import * as animateScroll from 'svelte-scrollto'
</script>

<template>
    <section class="welcome">
        <div class="image-background" />
        <div class="content">
            <div class="title">
                <div class="fill" />
                <h1 class="h1">ESNdictionary</h1>
                <h2 class="h5">Get to know all the ESN slang in one place.</h2>
                <p>
                    Navigate by pressing a key on the keyboard or by using the
                    menu on the left.
                </p>
                <div class="fill" />
            </div>
            <div
                on:click={() =>
                    animateScroll.scrollTo({
                        element: '#anchor-a',
                    })}
                class="button button--secondary button--inverse"
            >
                Get started
            </div>
            <div
                class="mouse-scroll"
                on:click={() =>
                    animateScroll.scrollTo({
                        element: '#anchor-a',
                    })}
            >
                <div class="mouse">
                    <div class="mouse-movement" />
                </div>
                <span class="mouse-message">scroll</span>
            </div>
        </div>
    </section>
</template>

<style lang="scss">
    $border--radius: 0.25rem;
    $color-brand-primary: #2e3192;
    $color__text--inverse: rgba(255, 255, 255, 0.85) !default;
    $easing--secondary: cubic-bezier(0.25, 0.1, 0.25, 1) !default;

    @keyframes scroll-ani {
        0% {
            opacity: 1;
            top: 29%;
        }
        15% {
            opacity: 1;
            top: 50%;
        }
        50% {
            opacity: 0;
            top: 50%;
        }
        100% {
            opacity: 0;
        }
    }

    @keyframes fadeIn {
        0% {
            opacity: 0;
        }
        100% {
            opacity: 1;
        }
    }

    .welcome {
        color: $color__text--inverse;
        background-color: $color-brand-primary;
        min-height: 100vh;
        margin-left: 1.5rem;

        .image-background {
            z-index: 2;
            position: absolute;
            top: 0;
            bottom: 0;
            left: 0;
            right: 0;
            background-repeat: no-repeat;
            background-size: cover;
            background-position: center;
            transition: all 10s $easing--secondary;
            animation: fadeIn 2s ease-in;

            // TODO Import as static asset
            background-image: url('https://images.unsplash.com/photo-1445445290350-18a3b86e0b5a?crop=entropy&dpr=2&fit=crop&fm=jpg&h=925&ixjsv=2.1.0&ixlib=rb-0.3.5&q=50&w=1675');
            background-color: transparentize($color-brand-primary, 0.1);
            background-blend-mode: multiply;
        }

        .content {
            z-index: 3;
            position: absolute;
            top: 0;
            bottom: 0;
            left: 0;
            right: 0;
            margin: auto;
            display: flex;
            flex-direction: column;
            justify-content: space-around;
            text-align: center;

            .title {
                flex-basis: 70%;
                display: flex;
                flex-direction: column;
                > * {
                    margin: 1vh;
                }
                .fill {
                    flex-grow: 1;
                }
            }
            .button {
                max-width: 400px;
                margin: auto auto 10vh;
                border-radius: $border--radius;
                line-height: 1rem;
                font-weight: bolder;
                text-transform: uppercase;
                cursor: pointer;
                letter-spacing: 0.1em;
                transition: all 0.25s cubic-bezier(0.25, 0.1, 0.25, 1);
                font-size: 0.75rem;

                padding: 1em;
                outline: 2px solid white;

                &:hover {
                    background-color: white;
                    color: #2e3192;
                }
            }
            .mouse-scroll {
                flex-basis: 30%;
                height: 100%;

                @media screen and (max-width: 992px) {
                    display: none;
                }

                .mouse {
                    margin: auto;
                    width: 30px;
                    height: 50px;

                    position: relative;
                    display: block;
                    box-sizing: border-box;
                    border: 3px solid #fff;
                    border-radius: 23px;

                    .mouse-movement {
                        position: absolute;
                        display: block;
                        top: 29%;
                        left: 50%;
                        width: 8px;
                        height: 8px;
                        margin: -4px 0 0 -4px;
                        background: #fff;
                        border-radius: 50%;
                        animation: scroll-ani 3s linear infinite;
                    }
                }

                .mouse-message {
                    color: white;
                    display: none;
                    margin-top: 1vh;
                    animation: scroll-ani 3s linear infinite;
                }

                &:hover .mouse-message {
                    display: block;
                }
            }
        }
    }
</style>

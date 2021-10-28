<script lang="ts">
    import * as animateScroll from 'svelte-scrollto'
</script>

<template>
    <section class="welcome">
        <div class="image-background" />
        <div class="content">
            <div class="container-fluid row">
                <div class="col-xs-12">
                    <h1 class="h1">ESNdictionary</h1>
                    <h2 class="h5">
                        Get to know all the ESN slang in one place.
                    </h2>
                    <p class="rhythm">
                        Navigate by pressing a key on the keyboard or by using
                        the menu on the left.
                    </p>
                    <a
                        on:click={() =>
                            animateScroll.scrollTo({
                                element: '#anchor-a',
                            })}
                        class="button button--large button--secondary button--inverse"
                        >Get started</a
                    >
                </div>
            </div>
        </div>
        <a
            class="mouse-scroll"
            on:click={() =>
                animateScroll.scrollTo({
                    element: '#anchor-a',
                })}
        >
            <span class="mouse">
                <span class="mouse-movement" />
            </span>
            <span class="mouse-message">scroll</span>
        </a>
    </section>
</template>

<style lang="scss">
    $color-brand-primary: #2e3192;
    $color__text--inverse: rgba(255, 255, 255, 0.85) !default;
    $easing--secondary: cubic-bezier(0.25, 0.1, 0.25, 1) !default;

    .welcome {
        color: $color__text--inverse;
        overflow: hidden;
        min-height: 100vh;
        position: relative;
        text-align: center;
        background-color: $color-brand-primary;
        & * {
            text-shadow: none !important;
        }

        .image-background {
            position: absolute;
            width: 100%;
            height: 100%;
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
            position: absolute;
            top: 50%;
            width: 100%;
            transform: translateY(-50%);
        }
    }

    .mouse-scroll {
        position: absolute;
        bottom: 2vh;
        transform: translateX(-50%);

        @media screen and (max-width: 992px) {
            display: none;
        }

        .mouse {
            position: relative;
            display: block;
            width: 30px;
            height: 50px;
            margin: 0 auto 20px;
            -webkit-box-sizing: border-box;
            -moz-box-sizing: border-box;
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
                animation: 'scroll-ani 3s linear infinite';
            }
        }

        .mouse-message {
            float: left;
            color: transparent;
            margin-top: -15px;
            padding: 0;
            animation: 'scroll-ani 3s linear infinite';

            // Only show message if we are hovering the parent
            :hover > & {
                color: white;
            }
        }
    }
</style>

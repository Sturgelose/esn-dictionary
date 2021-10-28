<script lang="ts">
    import * as animateScroll from 'svelte-scrollto'

    const alphabet = [
        'A',
        'B',
        'C',
        'D',
        'E',
        'F',
        'G',
        'H',
        'I',
        'J',
        'K',
        'L',
        'M',
        'N',
        'O',
        'P',
        'Q',
        'R',
        'S',
        'T',
        'U',
        'V',
        'W',
        'X',
        'Y',
        'Z',
        '#',
    ]
</script>

<template>
    <section class="navbar vertical">
        {#each alphabet as char, i}
            <div
                class="navitem"
                on:click={() =>
                    animateScroll.scrollTo({
                        element: '#anchor-' + char.toLowerCase(),
                    })}
            >
                {char}
            </div>
        {/each}
    </section>
</template>

<style lang="scss">
    $color-brand-primary: #2e3192;

    .navbar {
        font-weight: bold;
        display: flex;
        align-items: center;
        justify-content: space-between;
        transform: translateY(0);
        transition: transition--secondary-short;
        &.vertical {
            color: $color-brand-primary;
            flex-direction: column;
            position: fixed;
            z-index: 1000;
            top: 0;
            left: 0;
            height: 100vh;
            background-color: white;
            & .nav__item {
                margin: 0 !important;
            }
            &.navbar--hidden {
                transform: translateX(-100%);
            }
        }
    }

    .navitem {
        position: relative;
        display: flex;
        align-items: center;

        font-size: 0.5rem;
        padding: 0.5rem;

        &:hover {
            transform: scale(2);
            background-color: $color-brand-primary;
            color: white;
            z-index: 1000;
        }
    }
</style>

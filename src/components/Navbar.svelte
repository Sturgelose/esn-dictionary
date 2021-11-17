<script lang="ts">
    import * as animateScroll from 'svelte-scrollto'
    import { ALPHABET } from '../constants'
</script>

<template>
    <section class="navbar">
        {#each ALPHABET as char, i}
            <div
                class="navitem"
                on:mouseover={() =>
                    animateScroll.scrollTo({
                        element: '#anchor-' + char.toLowerCase(),
                    })}
                on:focus={() =>
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
        display: flex;
        align-items: center;
        justify-content: space-evenly;
        flex-direction: column;
        position: fixed;
        z-index: 1000;
        top: 0;
        left: 0;
        bottom: 0;

        .navitem {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 1.5rem;
            background-color: white;
            color: $color-brand-primary;
            font-weight: bold;
            height: 100%;
            font-size: 0.5rem;
            cursor: pointer;

            &:hover {
                background-color: $color-brand-primary;
                color: white;
                transform: scale(2);
                z-index: 1000;
            }
        }
    }
</style>

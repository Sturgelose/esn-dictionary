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
    <section class="navbar navbar--vertical font__weight--bold" id="navbi">
        {#each alphabet as char, i}
            <div
                on:click={() =>
                    animateScroll.scrollTo({
                        element: '#anchor-' + char.toLowerCase(),
                    })}
                class="nav__item nav__item--padded nav__item--small nav__item--zoom nav__item--hover"
            >
                {char}
            </div>
        {/each}
    </section>

    <!--	<section class='navbar navbar&#45;&#45;vertical2 font__weight&#45;&#45;bold' id='navbi2' style='padding-bottom:2000px !important'>-->
    <!--		{#each alphabet as char, i}-->
    <!--			<div class='nav__item nav__item&#45;&#45;padded nav__item&#45;&#45;small nav__item&#45;&#45;zoom nav__item&#45;&#45;hover'><a-->
    <!--				href='#{char.toLowerCase()}'>{char}</a></div>-->
    <!--		{/each}-->
    <!--	</section>-->
</template>

<style lang="scss">
</style>

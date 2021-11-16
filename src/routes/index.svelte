<script lang="ts">
    import Navbar from '../components/Navbar.svelte'
    import Welcome from '../components/Welcome.svelte'
    import Dictionary from '../components/Dictionary.svelte'

    export const prerender = true;
</script>

<template>
    <Navbar />
    <Welcome />
    <Dictionary />
</template>

<style lang="scss" global>
    @import 'static/styles/index';
</style>

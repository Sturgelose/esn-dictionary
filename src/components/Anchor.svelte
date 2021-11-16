<script lang="ts">
    export let character: string
</script>

<template>
    <div class="anchor" id="anchor-{character.toLowerCase()}">
        ANCHOR {character.toUpperCase()}
    </div>
</template>

<style lang="scss">
    .anchor {
        max-width: 75%;
        margin: 1rem auto;
    }
</style>

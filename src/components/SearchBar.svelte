<template>
    <input
        id="searchbar"
        onkeyup="search_animal()"
        type="text"
        name="search"
        placeholder="Search words.."
    />
</template>

<style lang="scss">
    $rhythm: 1rem !default;
    $border__width: 1px !default;

    input[type='text'] {
        line-height: $rhythm;
        border-width: 2 * $border__width;
        padding: unquote('calc(.5rem - #{$border__width})');
    }

    #searchbar {
        max-width: 500px;
        width: 75%;
        display: block;
        text-align: center;
        margin: 50px auto auto;
    }
</style>

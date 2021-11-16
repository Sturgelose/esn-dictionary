<script lang="ts">
    import Anchor from './Anchor.svelte'
    import DictionaryEntry from './DictionaryEntry.svelte'
    import { onMount } from 'svelte'

    let dictionaryEntries: Array<DictionaryEntry> = []

    onMount(async () => {
        const request = await fetch(
            'https://docs.google.com/spreadsheets/d/1vUFUH1GR7oKEVxUNtkJ_kFaj5FvgJIWecJMivB07kSo/gviz/tq?tqx=out:json'
        )
        dictionaryEntries = processDataFromJsonp(await request.text())
    })

    function processDataFromJsonp(request): Array<DictionaryEntry> {
        const regex = /google\.visualization\.Query\.setResponse\(([\s\S\w]+)\)/
        const parsed = request.match(regex)
        if (parsed && parsed.length === 2) {
            const rows = JSON.parse(parsed[1]).table.rows
            rows.shift()
            return rows.map(
                (row) =>
                    ({
                        term1: row.c[0]?.v,
                        term2: row.c[1]?.v,
                        grammar: row.c[2]?.v,
                        definition: row.c[3]?.v,
                        example: row.c[4]?.v,
                        category: row.c[5]?.v,
                        anchor: row.c[6]?.v,
                    } as DictionaryEntry)
            )
        }
    }
</script>

<template>
    <div class="dictionary">
        <!--			<SearchBar />-->

        {#await dictionaryEntries}
            <p>...waiting</p>
        {:then data}
            {#each dictionaryEntries as entry, i}
                {#if entry.anchor}
                    <Anchor character={entry.anchor} />
                {/if}
                <DictionaryEntry {entry} />
            {/each}
        {:catch error}
            <p>An error occurred!</p>
        {/await}
    </div>
</template>

<style lang="scss">
    .dictionary {
        display: flex;
        flex-direction: column;
    }
</style>

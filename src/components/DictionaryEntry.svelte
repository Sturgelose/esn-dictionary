<script lang="ts">
    import type { DictionaryEntry } from './DictionaryEntry'

    export let entry: DictionaryEntry
</script>

<template>
    <div>
        <div class="entry card animate">
            <div class="content">
                <p class="h6">{entry.term1}</p>
                <p class="entries2">{entry.term2}</p>
                <p class="type">{entry.category}</p>
                <p class="grammar">{entry.grammar}</p>
                <ol class="explanation">
                    <li>
                        <span class="description">{entry.definition}</span>
                        <br />
                        <span class="usage">{entry.example}</span>
                    </li>
                </ol>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    $color-brand-primary: #2e3192;
    $border--radius: 0.25rem;

    .card {
        padding-top: 1rem;
        padding-bottom: 1rem;
        border-radius: $border--radius;
    }

    .entry {
        .anchor {
        }
        .content {
            .phrase {
                font-weight: bold;
                font-size: 1rem;
                color: $color-brand-primary;
            }
            .type {
                font-family: Georgia;
                font-style: italic;
            }
            .grammar {
            }
            .entries2 {
            }
            .explanation {
                font-family: Georgia;
                margin-top: 1rem;
                padding: 0 0.25rem;
                & > li:before {
                    display: inline-block;
                    width: 1em;
                    padding-right: 0.5em;
                    font-weight: bold;
                    text-align: right;
                    content: counter(item) '';
                }
                & > li {
                    list-style-type: none;
                    counter-increment: item;
                }
                .description {
                    color: $color-brand-primary;
                    font-family: sans-serif;
                    &:after {
                        content: ':';
                    }
                }
                .usage {
                    display: inline-block;
                    padding-top: 0.25rem;
                    font-style: italic;
                }
            }
        }
    }
</style>

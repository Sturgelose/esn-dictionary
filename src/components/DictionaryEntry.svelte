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
        position: relative;
        background-color: white;
        overflow: hidden;
        border: none;
        box-shadow: 0 0 50px rgba(0, 0, 0, 0.2);
        transition: all 0.25s cubic-bezier(0.6, 0.2, 0.1, 1);
        &:hover {
            box-shadow: 0 0 50px * 1.25 rgba(0, 0, 0, 0.2);
            transform: translateY(-0.125rem);
        }
        max-width: 75%;
        margin: 1rem auto;
        padding: 1rem;
        border-radius: $border--radius;
    }

    .entry {
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

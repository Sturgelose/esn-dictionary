<script lang="ts">
	import type { DictionaryEntry } from './DictionaryEntry';

	export let entry: DictionaryEntry;
</script>

<template>
	<div>
		<div class="entry card animate">
			<div class="content">
				<p class="entries2">{entry.term2}</p>
				<p class="h6">{entry.term1}</p>
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
	.entry {
		.anchor {
		}
		.content {
			.phrase {
			}
			.type {
			}
			.grammar {
			}
			.entries2 {
			}
			.explanation {
				.description {
				}
				.usage {
				}
			}
		}
	}
</style>

<template>
	<footer class="bg-discord-weeby-1000">
		<div class="max-w-3xl mx-auto text-center px-16 pt-10 pb-4 text-gray-200">
			<strong><router-link to="/">weeby-js</router-link></strong>
			<p class="mb-4">The official JavaScript API Wrapper for Weeby API.</p>
			<Stats class="mb-4" />
			<p class="mb-4">Website design by <a href="https://discord.js.org/">Discord.js</a></p>
			<p class="text-xs break-words-legacy">
				commit: {{ gitCommit }}<br />
				built at: {{ builtAt }}
			</p>
		</div>
	</footer>
</template>

<script setup lang="ts">
import { ref } from 'vue';

import Stats from './Stats.vue';

declare const GIT_COMMIT_HASH: string;
declare const BUILT_AT: string;

const gitCommit = ref(GIT_COMMIT_HASH);
const builtAt = ref(new Date(BUILT_AT).toUTCString());
</script>

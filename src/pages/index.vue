<template>
	<div class="bg-discord-weeby-800 py-20">
		<div class="max-w-3xl sm:mx-auto text-center px-8 sm:px-16 flex flex-col gap-10 md:px-12">
			<Logo class="filter drop-shadow-lg my-6" />
			<InstallButton />
		</div>
	</div>

	<div
		class="
			prose prose-discord
			dark:prose-light
			lg:prose-lg
			px-6
			mx-auto
			pb-8
			w-full
			xl:grid xl:grid-cols-2 xl:gap-x-12 xl:max-w-7xl
		"
	>
		<div class="col-span-full">
			<h2>About</h2>
			<p>
				Weeby-JS is the official JavaScript API Wrapper which is powerful and allows easy interaction with the
				<a href="https://weebyapi.xyz/" target="_blank" rel="noopener"
					>Weeby API <heroicons-outline-external-link class="h-5 w-5 inline-block mb-1" aria-hidden="true"
				/></a>
				endpoints. Actively maintained by
				<a href="https://dev.ntmcentral.xyz/" target="_blank" rel="noopener"
					>NTM Development <heroicons-outline-external-link class="h-5 w-5 inline-block mb-1" aria-hidden="true"
				/></a>
				and community members, Weeby-JS receives new updates shortly after new features have been released to the API.
			</p>
		</div>
		<div>
			<h2>Why?</h2>
			<ul>
				<li>Super simple and easy to use</li>
				<li>Built in Documentation</li>
				<li>Includes all methods from Weeby API</li>
				<li>Object-oriented</li>
				<li>Beginner friendly</li>
				<li>Support for TypeScript</li>
			</ul>
		</div>
		<div>
			<h2>Statistics</h2>
			<Stats />
			<p class="text-center">... and growing!</p>
		</div>
	</div>
</template>

<script setup lang="ts">
import { computed } from 'vue';

import { useStore } from '~/store';
import MainSource from '~/data/MainSource';

import Logo from '~/components/Logo.vue';
import InstallButton from '~/components/InstallButton.vue';
import Stats from '~/components/Stats.vue';

const store = useStore();

const docs = computed(() => store.state.docs);

if (!docs.value) {
	void store.dispatch('fetchDocs', { inputSource: MainSource });
	void store.dispatch('fetchTags', { currentSource: MainSource });
}
</script>

<script lang="ts">
	import { page } from '$app/stores';

	let pages = [
		{
			icon: '🗓️',
			path: '/'
		},
		{
			icon: '📝',
			path: '/day'
		},
		{
			icon: '🎯',
			path: '/goals'
		},
		{
			icon: '📈',
			path: '/stats'
		}
	];
</script>

<div class="flex border rounded-lg w-min mb-2 p-1 gap-1">
	{#each pages as p}
		{#if p.path == $page.url.pathname}
			<a class="rounded-md py-1 px-4 bg-gray-100 cursor-pointer" href={p.path}>
				{p.icon}
			</a>
		{:else}
			<a class="rounded-md py-1 px-4 cursor-pointer hover:bg-gray-50 transition" href={p.path}>
				{p.icon}
			</a>
		{/if}
	{/each}
</div>

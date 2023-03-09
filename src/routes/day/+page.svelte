<script lang="ts">
	import Button from '$lib/components/Button.svelte';
	import Card from '$lib/components/Card.svelte';

	let content: string = '';

	const test = (mood: string) => {
		console.log(mood);
	};
</script>

<Card>
	<div class="grid">
		<h2 class="text-gray-800 mb-2 text-lg">How was your day?</h2>
		<div class="flex gap-2 justify-between">
			{#each ['🙁', '😐', '🙂'] as mood}
				<Button on:click={() => test(mood)}>
					<span class="text-xl">
						{mood}
					</span>
				</Button>
			{/each}
		</div>
		<textarea
			class="mt-1 text-sm"
			cols="30"
			rows="10"
			placeholder="Type here..."
			bind:value={content}
		/>
	</div>
</Card>

<Card>
	<h2 class="text-gray-800 mb-2 text-lg">Goals</h2>
	<div class="flex gap-1">
		<label for="guitar" class="text-sm text-gray-600">
			<input id="guitar" type="checkbox" class="" />
			Practice guitar
		</label>
		<!-- <span>🔥4</span> -->
	</div>
	<div class="flex gap-1">
		<label for="gym" class="text-sm text-gray-600">
			<input id="gym" type="checkbox" class="" />
			Go to the gym
		</label>
		<!-- <span>🔥2</span> -->
	</div>
</Card>

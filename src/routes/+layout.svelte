<script>
	import '../app.css';

	import Navigation from '$lib/components/Navigation.svelte';
</script>

<div class="flex justify-center mt-32 min-h-screen">
	<div>
		<Navigation />
		<div class="grid grid-cols-2 gap-4">
			<slot />
		</div>
	</div>
</div>

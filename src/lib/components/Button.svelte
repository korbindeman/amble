<script>
	let buttonProps = {
		class: [$$restProps.class]
	};
</script>

<button
	on:click
	on:mouseover
	on:focus
	on:mouseenter
	on:mouseleave
	{...buttonProps}
	class="bg-gray-100 p-2 hover:bg-gray-200 w-full rounded transition focus:bg-blue-200"
>
	<slot />
</button>

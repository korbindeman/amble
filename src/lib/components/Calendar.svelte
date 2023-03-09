<script lang="ts">
	import dayjs from 'dayjs';
	import localeData from 'dayjs/plugin/localeData';
	dayjs.extend(localeData);

	let month = dayjs().month();

	$: firstDay = parseInt(dayjs().month(month).startOf('month').format('d'));

	const changeMonth = (delta: number) => {
		month += delta;
	};

	const today = () => {
		month = dayjs().month();
	};
</script>

<div class="">
	<div class="flex justify-between">
		<div class="text-lg mb-2 flex justify-between w-full">
			<span class="">
				{dayjs().month(month).format('MMMM YYYY')}
			</span>
			<div class="">
				<button class="" on:click={() => changeMonth(-1)}>⬅️</button>
				<button class="" on:click={today}>↩️</button>
				<button class="" on:click={() => changeMonth(1)}>➡️</button>
			</div>
		</div>
	</div>

	<div class="grid grid-cols-7 gap-2">
		{#each dayjs.weekdaysShort() as weekday}
			<div class="w-full text-center text-sm text-gray-600">
				{weekday}
			</div>
		{/each}
		{#each [...Array(firstDay)] as _}
			<div class="h-8 w-8" />
		{/each}
		{#each [...Array(dayjs().month(month).daysInMonth()).keys()] as date}
			{#if date + 1 == dayjs().date() && dayjs().month(month).month() == dayjs().month()}
				<div
					class="h-8 w-8 grid place-content-center border-2 border-blue-700 leading-none rounded-xl text-sm hover:bg-blue-50 transition cursor-pointer"
				>
					{date + 1}
				</div>
			{:else}
				<div
					class="h-8 w-8 grid place-content-center border-2 leading-none rounded-xl text-sm hover:bg-gray-50 transition cursor-pointer"
				>
					{date + 1}
				</div>
			{/if}
		{/each}
	</div>
</div>

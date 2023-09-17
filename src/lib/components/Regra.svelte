<script lang="ts">
	import {Input} from './ui/input'
	import autoAnimate from '@formkit/auto-animate'

	let value1: number
	let value2: number
	let value3: number

	$: result = Number(((value3 * value2) / value1).toFixed(2))
</script>

<main use:autoAnimate class="grid place-content-center gap-4 font-mono">
	<h1 class="text-4xl text-center font-extrabold">Proportion Rule</h1>
	<section class="grid grid-cols-2 gap-4">
		<Input type="number" bind:value={value1} />
		<Input type="number" bind:value={value2} />
		<Input type="number" bind:value={value3} />
		<Input type="number" bind:value={result} disabled />
	</section>

	{#if result}
		{#key result}
			<p class="text-center text-2xl font-bold font-mono">
				{value3} is for {result} as {value1} is for {value2}
			</p>
		{/key}
	{/if}
</main>

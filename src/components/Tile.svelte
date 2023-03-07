<script lang="ts">
	export let x: number;
	export let y: number;
	export let size: number;
</script>

<div class="tile">
	{#if y !== 0}
		<div class="north" />
	{/if}
	{#if x < size - 1}
		<div class="east" />
	{/if}
	<div class="center" />
	{#if y < size - 1}
		<div class="south" />
	{/if}
	{#if x !== 0}
		<div class="west" />
	{/if}
</div>

<style lang="scss">
	.tile {
		display: grid;
		grid-template-rows: 20px 5px 20px;
		grid-template-columns: 20px 5px 20px;
		grid-template-areas:
			'.    north .    '
			'west center east'
			'.    south .    ';

		> div {
			background-color: black;
		}

		.north {
			grid-area: north;
		}

		.east {
			grid-area: east;
		}

		.center {
			grid-area: center;
		}

		.south {
			grid-area: south;
		}

		.west {
			grid-area: west;
		}
	}
</style>

<script lang="ts">
	import Tile from './Tile.svelte';

	export let size = 19;
</script>

<div class="board">
	{#each { length: size } as _, y}
		<div class="row">
			{#each { length: size } as _, x}
				<Tile {x} {y} {size} />
			{/each}
		</div>
	{/each}
</div>

<style lang="scss">
	.board {
		display: flex;
		flex-flow: column nowrap;

		.row {
			display: flex;
			flex-flow: row nowrap;
		}
	}
</style>

<script>
	export let popular
	import MovieCard from './MovieCard.svelte'
</script>

<div class="popular-movies">
	{#each popular as movie}
		<MovieCard movie="{movie}" />
	{/each}
</div>

<style>
	.popular-movies {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		align-items: center;
	}
</style>

<script context="module">
	export async function load({ fetch, params }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/search/movie?api_key=${connectionString}&language=en-US&query=${params.id}&page=1&include_adult=false`
		)
		const data = await res.json()
		if (res.ok) {
			return {
				props: { searchedMovie: data.results }
			}
		}
	}
</script>

<script>
	import MovieCard from '$lib/components/MovieCard.svelte'
	import { connectionString } from '$lib/dbURL'

	export let searchedMovie
</script>

<div class="searched-movies">
	{#each searchedMovie as movie}
		<MovieCard movie="{movie}" />
	{/each}
</div>

<style>
	.searched-movies {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		align-items: center;
	}
</style>

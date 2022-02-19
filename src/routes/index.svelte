<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/popular?api_key=${connectionString}&language=en-US&page=1`
		)
		const data = await res.json()
		if (res.ok) {
			return {
				props: { popular: data.results }
			}
		}
	}
</script>

<script>
	import PopularMovie from '$lib/components/PopularMovie.svelte'
	import SearchMovies from '$lib/components/SearchMovies.svelte'
	import { connectionString } from '$lib/dbURL'
	import { fly } from 'svelte/transition'
	export let popular
</script>

<section in:fly="{{ y: 50, duration: 300, delay: 300 }}" out:fly="{{ duration: 300 }}">
	<SearchMovies />
	<PopularMovie popular="{popular}" />
</section>

<style>
	section {
		text-align: center;
	}
</style>

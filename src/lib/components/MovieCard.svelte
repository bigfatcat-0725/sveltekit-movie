<script>
	export let movie
</script>

<div class="movie-card">
	<a sveltekit:noscroll sveltekit:prefetch href="{`/movie/${movie.id}`}">
		<img src="{`https://image.tmdb.org/t/p/w500${movie.poster_path}`}" alt="{movie.title}" />
	</a>
	<div class="description">
		<h2>{movie.title}</h2>
		<p>{movie.release_date}</p>
	</div>
</div>

<style>
	.movie-card {
		display: flex;
		flex-direction: column;
		padding: 5px;
		margin-bottom: 1rem;
	}
	img {
		width: 20rem;
		min-width: 20rem;
		min-height: 30rem;
		border-radius: 20px;
		margin-bottom: 1vh;
	}
	.description {
		height: 5vh;
	}
	h2 {
		font-size: 1rem;
		margin-top: 0;
		margin-bottom: 1rem;
	}
	p {
		font-size: 0.8rem;
		margin: 0;
	}
</style>

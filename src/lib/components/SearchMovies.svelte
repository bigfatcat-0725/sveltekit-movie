<script>
	import { goto } from '$app/navigation'

	let inputValue = ''

	function submitSearch(e) {
		if (e.keyCode === 13) {
			console.log('hi')
			goto(`/search/${inputValue}`)
		}
	}
</script>

<input
	type="text"
	placeholder="search and enter"
	bind:value="{inputValue}"
	on:keypress="{submitSearch}"
	autocomplete="off"
/>

<style>
	input {
		width: 35%;
		border: none;
		font-size: 0.8rem;
		outline: none;
		color: black;
		transition: background 0.75s ease-out;
		background: white;
		border-radius: 10px;
		padding: 0.7rem;
		margin: 1rem;
		text-align: center;
	}
	input::placeholder {
		color: gray;
		font-size: 0.8rem;
	}
</style>

<script>
	import Loader from "./Loader.svelte";
	import  wordData from "./WordData.svelte"
	let word = "";
	let loading = false;
	let wordData = null;
  
	async function searchWord() {
	  if (word.length === 0) {
		return;
	  }
	  loading = true;
	  wordData = null;
  
	  try {
		let res = await fetch("https://api.dictionaryapi.dev/api/v2/entries/en/" + word);
		let data = await res.json();
		if (Array.isArray(data)) {
		  wordData = data[0];
		} else {
		  wordData = "No Result";
		}
	  } catch (err) {
		loading = false;
	  }
	}
  </script>
  
  <style>
	/* Add your styles here */
  </style>
  
  <div class="header">Dictionary App</div>
  <div class="center">
	<div class="form">
	  <div class="form-group">
		<label for="Search Word"></label>
		<input type="text" placeholder="Type word here" bind:value={word} />
	  </div>
	  <div class="form-group">
		<button on:click={searchWord}>Search</button>
	  </div>
	</div>
	{#if loading == true || wordData != null}
	  <div class="result">
		{#if wordData != null && typeof wordData !== 'string'}
		  <p>Found Data</p>
		{:else if wordData === null && loading === true}
		  <Loader />
		{:else}
		  <p class="padding">No result Found</p>
		{/if}
	  </div>
	{/if}
  </div>
  <main></main>
  
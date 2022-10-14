<script>
  import Movie from "./Movie.svelte";

  let value = "";
  let loading = false;
  let response = [];

  const handleInput = (event) => (value = event.target.value);

  $: if (value.length > 2) {
    loading = true;
    fetch(`http://www.omdbapi.com/?s=${value}&apikey=bc2125e`)
      .then((res) => res.json())
      .then((apiResponse) => {
        response = apiResponse.Search || [];
        loading = false;
      });
  }
</script>

<input placeholder="Search movies..." {value} on:input={handleInput} />

{#if loading}
  <strong>loading...</strong>
{:else}
  {#each response as { Title, Poster, Year }}
    <Movie title={Title} poster={Poster} year={Year} />
  {:else}
    <strong>We not found results</strong>
  {/each}
{/if}

<style>
</style>

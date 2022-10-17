<script>
  import Movie from "./Movie.svelte";

  let value = "";
  let response = [];

  const handleInput = (event) => (value = event.target.value);

  $: if (value.length > 2) {
    fetch(`http://www.omdbapi.com/?s=${value}&apikey=bc2125e`)
      .then((res) => res.json())
      .then((apiResponse) => {
        response = apiResponse.Search || [];
      });
  } else {
    response = [];
  }
</script>

<input placeholder="Search movies..." {value} on:input={handleInput} />

{#await response}
  <strong>loading...</strong>
{:then}
  {#each response as { Title, Poster, Year, Genre }}
    <Movie title={Title} poster={Poster} year={Year} genre={Genre} />
  {:else}
    <strong>We not found results</strong>
  {/each}
{/await}

<style>
  input{
    width: 100%;
    padding: 1rem;
    border-radius: 5px;
    margin: 2rem;
    background: antiquewhite;
    color: black;
    text-transform: uppercase;
  }
  
</style>

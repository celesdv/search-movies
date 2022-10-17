<script>
  export let title, poster, year, type;
</script>

<article>
  <h3>{title}</h3>
  <img src={poster} alt={title} /> 
  <p>
    <span>Year: {year} </span>
    {#if 2020 - year < 5}
      <i>New! ✨ </i>
    {/if}
    <span>
     {type} 
    </span>
  </p> 
</article>

<style>
  article {
    width: 100%;
    padding: 1rem;
    margin: 2rem;
  }
</style>

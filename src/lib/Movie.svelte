<script>
  export let title, poster, year;
</script>

<article>
  <img src={poster} alt={title} />
  <h3>{title}</h3>
  <span>{year}</span>
  {#if 2020 - year < 5}
    <i>New!</i>
  {/if}
</article>

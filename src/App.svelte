<script>
  let name = "World";

  import Input from "./lib/Input.svelte";

  setTimeout(function () {
    name = "Celeste";
  }, 5000);
</script>

<main>
  <h1>Search movies 🍿</h1>
  <h2>Hello {name}!!</h2>
  <Input />
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1{
    text-transform: uppercase;
    font-weight: 100;
    margin-left: 4rem;
  }
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

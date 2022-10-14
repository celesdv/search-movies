<script>
  let name = "World";

  import Input from "./lib/Input.svelte";

  setTimeout(function () {
    name = "Celeste";
  }, 5000);
</script>

<main>
  <h1>Movie Search</h1>
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

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

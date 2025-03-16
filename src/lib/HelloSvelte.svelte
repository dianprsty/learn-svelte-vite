<script>
  import Landscape from "./components/Landscape.svelte";
  const name = "Svelte";

  const content = '<h2>HTML content</h2>';
</script>

<h1>
  Hello {name.toUpperCase()}
</h1>
{@html content}

<Landscape />


<style>
  h1 {
    color: red;
  }


</style>

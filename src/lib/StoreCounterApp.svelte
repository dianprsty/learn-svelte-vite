<script>
  import StoreCounter from "./components/StoreCounter.svelte";
</script>
<h2>Counter Using Store</h2>
<section>
  <StoreCounter />
  <StoreCounter />
  <StoreCounter />
  <StoreCounter />
</section>

<style>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 1rem;
    margin: 1rem 0;
  }
</style>

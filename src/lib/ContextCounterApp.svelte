<script>
  import { setContext } from "svelte";
  import ContextCounter from "./components/ContextCounter.svelte";

  const counter = $state({ count: 0 });

  setContext("counter", counter);
</script>

<section>
  <ContextCounter />
  <ContextCounter />
  <ContextCounter />
  <ContextCounter />
  <ContextCounter />
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

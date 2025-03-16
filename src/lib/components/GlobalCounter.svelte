<script>
  import { counter } from "../state/counter.svelte";

  const increment = () => {
    counter.count++;
  };

  const decrement = () => {
    counter.count--;
  };
</script>

<section>
  <button onclick={decrement}>-</button>
  <span>{counter.count}</span>
  <button onclick={increment}>+</button>
</section>

<style>
  section {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1rem;
    margin: 1rem 0;
  }
</style>

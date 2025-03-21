<script>
  import { getContext } from "svelte";

  const counter = getContext("counter");

  const increment = () => {
    counter.count++;
  };

  const decrement = () => {
    counter.count--;
  };
</script>

<span>
  <button onclick={decrement}>-</button>
  {counter.count}
  <button onclick={increment}>+</button>
</span>

<style>
  span {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1rem;
  }
</style>

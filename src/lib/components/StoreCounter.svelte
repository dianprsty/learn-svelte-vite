<script>
  import { counter } from "../state/counter.js";

  const increment = () => {
    $counter++;
  };

  const decrement = () => {
    $counter--;
  };
</script>

<section>
  <button onclick={decrement}>-</button>
  {$counter}
  <button onclick={increment}>+</button>
</section>

<style>
  section {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1rem;
  }
</style>

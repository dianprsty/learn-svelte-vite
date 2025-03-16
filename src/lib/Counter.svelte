<script>
  let count = $state([]);

  // $derived for single line / expression
  // let total = $derived(count.reduce((a, b) => a + b, 0));

  // $derived for multiline or if we need to do more complex logic
  let total = $derived.by(() => {
    let total = 0;

    for (let item of count) {
      total += item;
    }

    return total;
  });
  const increment = () => {
    count.push(1);
  };

  const decrement = () => {
    count.push(-1);
  };

  const reset = () => {
    count = [];
  };

  $inspect(count).with((type, value) =>{
    console.log(type, value)
  })
</script>

<main>
  <h2>Counter</h2>

  <section class="counter-group">
    <button onclick={decrement}> - </button>
    <p>
      {total}
    </p>

    <button onclick={increment}> + </button>
  </section>
  <button onclick={reset}> reset </button>

  <h2>History</h2>
  <p>
    {count.map((n) => (n > 0 ? `+${n}` : `${n}`)).join(", ")}
  </p>
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .counter-group {
    display: flex;
    gap: 2rem;
    margin-bottom: 2rem;
  }
</style>

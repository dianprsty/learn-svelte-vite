<script>
  let counter = $state(0);
  let interval = $state(1000);

  const increment = () => {
    interval += 100;
  };

  const decrement = () => {
    if (interval < 100) return;
    interval -= 100;
  }

  $effect(() => {
    const id = setInterval(() => {
      counter++;
    }, interval);

    return () => {
      clearInterval(id);
    };
  });
</script>

<main>
  <button onclick={decrement}>Decrement Interval: {interval} ms</button>
  <h1>Counter {counter}</h1>
  <button onclick={increment}>Increment Interval: {interval} ms</button>
</main>

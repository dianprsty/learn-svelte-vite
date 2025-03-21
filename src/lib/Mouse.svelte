<script>
  const mouse = $state({ x: 0, y: 0 });
  let message = $state("");

  const handleMouseMove = (event) => {
    mouse.x = event.clientX;
    mouse.y = event.clientY;
  };

  const handleClick = () => {
    message = `You Clicked (${mouse.x}, ${mouse.y})`;
  };
</script>

<svelte:body onmousemove={handleMouseMove} />
<svelte:document onclick={handleClick} />

<p>{message}</p>

<h1>X: {mouse.x}</h1>
<h1>Y: {mouse.y}</h1>

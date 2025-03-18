<script>
  const { id, name, done } = $props();

  // const emojis = {
  //   "1": "👍",
  //   "2": "👎",
  //   "3": "❤️",
  //   "4": "🤣",
  //   "5": "🚀",
  //   "6": "🤷"
  // }

  // const emoji = emojis[id];
  // console.log(emoji);
</script>

{#if done}
<span class="done">{id} - {name} </span>
{:else}
<span>{id} - {name} </span>
{/if}

<style>
  .done {
    text-decoration: line-through;
  }
  span {
    font-size: 20px;
  }
</style>

<script>
  let { id, name, onEdit } = $props();

  const save = () => {
    onEdit({
      id,
      value: name,
    });
  };
</script>

<span class="todo-row">
  {id} <input type="text" {id} bind:value={name} required />
  <button onclick={save}>Save</button>
</span>

<style>
  .todo-row {
    display: flex;
    gap: 0.5rem;
    align-items: center;
  }

  button {
    border-radius: 8px;
    border: 1px solid transparent;
    padding: 0.6em 1.2em;
    font-size: 1em;
    font-weight: 500;
    font-family: inherit;
    background-color: green;
    cursor: pointer;
    transition: border-color 0.25s;
  }

  button:hover {
    cursor: pointer;
  }
</style>

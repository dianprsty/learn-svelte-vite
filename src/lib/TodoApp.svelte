<script>
  import EditTodo from "./components/EditTodo.svelte";
  import Todo from "./components/Todo.svelte";
  import { fade, slide, fly } from "svelte/transition";

  let todos = $state([
    {
      id: 1,
      name: "Learn Svelte",
      done: false,
      edit: false,
    },
    {
      id: 2,
      name: "Learn Vite",
      done: false,
      edit: false,
    },
  ]);
  let name = $state("");
  let id = 3;

  const remove = (id) => {
    todos = todos.filter((todo) => todo.id !== id);
  };

  const add = (e) => {
    e.preventDefault();

    todos.push({
      id: id++,
      name: name,
      done: false,
      edit: false,
    });

    name = "";
  };

  const edit = (id) => {
    todos = todos.map((todo) => {
      if (todo.id === id) {
        todo.edit = true;
      }
      return todo;
    });
  };

  const onEdit = ({ id, value }) => {
    todos = todos.map((todo) => {
      if (todo.id === id) {
        todo.name = value;
        todo.edit = false;
      }
      return todo;
    });
  };
</script>

<h2>Add todo</h2>
<form onsubmit={add}>
  <input
    bind:value={name}
    type="text"
    name="todo"
    id="todo"
    placeholder="Type todo here"
    required
  />
  <button type="submit">Add</button>
</form>

{#snippet todoRow(todo)}
  <span
    in:fly={{ y: 100, duration: 1500 }}
    out:slide={{ duration: 750 }}
    onintrostart={() => console.log("intro start")}
    onoutrostart={() => console.log("outro start")}
    onintroend={() => console.log("intro end")}
    onoutroend={() => console.log("outro end")}
  >
    {#if todo.edit}
      <EditTodo id={todo.id} name={todo.name} {onEdit} />
    {:else}
      <span class="todo-list-group">
        <Todo {...todo} />
        <button onclick={() => edit(todo.id)}>Edit</button>
        <button onclick={() => remove(todo.id)}>Remove</button>
      </span>
    {/if}
  </span>
{/snippet}

<h2>List Todo</h2>

<section>
  {#each todos as todo (todo.id)}
    {@render todoRow(todo)}
  {/each}
</section>

<style>
  :global {
    input {
      height: 2rem;
      border-radius: 0.5rem;
      border: none;
      padding: 0.25rem 0.5rem;
    }
  }
  section {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    gap: 1rem;
    margin-bottom: 1rem;
  }

  .todo-list-group {
    display: flex;
    gap: 0.5rem;
    align-items: center;
  }
</style>

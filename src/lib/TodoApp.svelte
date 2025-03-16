<script>
  import Todo from "./components/Todo.svelte";

  const todos = $state([
    { id: 1, name: "Learn Svelte", done: true },
    { id: 2, name: "Learn SvelteKit", done: false },
    { id: 3, name: "Learn TypeScript", done: true },
    { id: 4, name: "Learn Vite", done: true },
    { id: 5, name: "Learn Tailwind", done: false },
    { id: 6, name: "Learn Prisma", done: false },
  ])

  const remove = () => {
      todos.shift();
  }
</script>

<h2>Todo</h2>

<section>
  {#each todos as todo (todo.id)}
    <Todo {...todo} />
  {/each}
</section>

<button onclick={remove}>Remove 🗑️</button>

<style>
  section {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    gap: 1rem;
    margin-bottom: 1rem;
  }
</style>

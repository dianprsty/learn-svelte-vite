<script>
  import { SvelteMap } from "svelte/reactivity";

  const students = new SvelteMap();

  let student = $state("");
  let value = $state(0);

  const addStudent = () => {
    students.set(student, value);
    student = "";
    value = 0;
  };
</script>

<div class="form-group">
  <span>
    Student <input type="text" bind:value={student} required />
  </span>
  <span>
    Value <input type="text" bind:value required />
  </span>
  <button onclick={addStudent}>Add Student</button>
</div>

<div>
  <table>
    <thead>
      <tr>
        <th>Student</th>
        <th>Value</th>
      </tr>
    </thead>
    <tbody>
      {#each students as entry (entry[0])}
        <tr>
          <td>{entry[0]}</td>
          <td>{entry[1]}</td>
        </tr>
      {/each}
    </tbody>
  </table>
</div>

<style>
  .form-group {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    margin-bottom: 2rem;
  }

  .form-group span {
    display: flex;
    gap: 1rem;
    flex-direction: column;
    text-align: start;
  }

  input {
    height: 2rem;
    border-radius: 0.5rem;
    border: none;
    padding: 0.25rem 0.5rem;
  }

  table{
    border-collapse: collapse;
  }

  td, th{
    padding-right: 1rem;
  }
</style>

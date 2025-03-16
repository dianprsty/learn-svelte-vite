<script>
  import UserRow from "./components/UserRow.svelte";

  const user = {
    id: 5,
    name: "Mark Smith",
    address: "321 Maple St",
  };
</script>

<h1>user data</h1>

<table>
  <thead>
    <tr>
      <th>id</th>
      <th>name</th>
      <th>address</th>
    </tr>
  </thead>
  <tbody>
    <UserRow id="1" name="John Doe" address="123 Main St" />
    <UserRow id="2" name="Jane Doe" address="456 Elm St" />
    <UserRow id="3" name="Bob Smith" address="789 Oak St" />
    <UserRow id="4" name="Alice Johnson" address="101 Pine St" />
    <UserRow {...user} />
  </tbody>
</table>

<style>
  table {
    border-collapse: collapse;
    width: 100%;
  }

  th {
    padding: 8px;
    text-align: left;
    border-bottom: 1px solid #ddd;
  }


</style>

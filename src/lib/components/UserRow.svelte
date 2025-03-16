<script>
  const { id, name, address } = $props();
</script>

<tr>
  <td>{id}</td>
  <td>{name}</td>
  <td>{address}</td>
</tr>

<style>
  td {
    padding: 5px;
    text-align: start;
  }

  
</style>

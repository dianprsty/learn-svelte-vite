<script>
  let person = $state({
    firstName: "",
    lastName: "",
  });

  const sayHello = () => {
    person.firstName = document.getElementById("firstName").value;
    person.lastName = document.getElementById("lastName").value;
  };
</script>

<main>
  <p>Say Hello</p>
  <input type="text" id="firstName" placeholder="First Name" />
  <input type="text" id="lastName" placeholder="Last Name" />
  <button onclick={sayHello}>Say Hello</button>

  <h1>
    {(person.firstName || person.lastName) && "Hello"}
    {person.firstName}
    {person.lastName}
  </h1>
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  input {
    display: block;
    height: 2rem;
    border-radius: 0.5rem;
    border: 1px solid #ccc;
    padding: 0 1rem;
    margin-bottom: 1rem;
  }
</style>

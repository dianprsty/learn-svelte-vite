<script>
  async function getArticle({ isError = false }) {
    // add  delay
    await new Promise((r) => setTimeout(r, 2000));

    const res = await fetch("/article.json");

    // simulate error
    if (isError) {
      throw new Error("Something went wrong");
    }

    return await res.json();
  }
</script>

{#await getArticle({ isError: false })}
  <p>Loading...</p>
{:then article}
  <h1>{article.title}</h1>
  <p>{article.content}</p>
{:catch error}
  <p>{error.message}</p>
{/await}

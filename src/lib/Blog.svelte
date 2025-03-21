<script>
  import { onDestroy, onMount } from "svelte";
  import Layout from "./Layout.svelte";

  let blog = $state({
    title: "",
    content: "",
    footer: "",
  });

  onMount(async () => {
    console.log("mounted");

    const response = await fetch("/blog.json");
    blog = await response.json();

    return () => {
      console.log("unmounted");
    };
  });

  onDestroy(() => {
    console.log("destroyed");
  });
</script>

<Layout title={blog.title} footer={blog.footer}>
  {#snippet content()}
    {@html blog.content}
  {/snippet}
</Layout>

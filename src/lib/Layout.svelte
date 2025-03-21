<script>
    const {title, content, footer} = $props();
</script>

<h2>{title}</h2>

<article>
    {@render content()}
</article>

<p>{footer}</p>
<!-- lib/Markdown.svelte -->
<script>
  import { marked } from "marked";

  export let rawMarkdown = "";
</script>

{@html marked(rawMarkdown)}

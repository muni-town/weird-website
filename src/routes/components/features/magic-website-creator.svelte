<script>
  import Card from "./card.svelte";
  import rawMarkdown from "./magic-website-creator.md?raw";
  import Markdown from "$lib/Markdown.svelte";
</script>

<Card>
  <span slot="icon">➢</span>
  <span slot="title">Magic Website Creator</span>

  <Markdown {rawMarkdown} slot="body" />
</Card>

<script>
  import Card from "./card.svelte";
  import rawMarkdown from "./web-passports.md?raw";
  import Markdown from "$lib/Markdown.svelte";
</script>

<Card>
  <span slot="icon">➣</span>
  <span slot="title">Web Passposts</span>

  <Markdown {rawMarkdown} slot="body" />
</Card>

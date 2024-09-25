<script>
  import Markdown from "$lib/Markdown.svelte";
  import YouTubeEmbed from "$lib/YouTubeEmbed.svelte";

  import rawMarkdown from "./video.md?raw";

  const videoId = "YgYKKCmcE04";
  const title = "Agentic Product Development - Erlend Sogge Heggen";
</script>

<div class="container">
  <Markdown {rawMarkdown} />
  <YouTubeEmbed {videoId} {title} />
</div>

<style>
  .container {
    padding-top: 12em;
    padding-bottom: 6em;
  }
</style>

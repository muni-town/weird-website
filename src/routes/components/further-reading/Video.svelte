<script>
  import Markdown from "$lib/Markdown.svelte";
  import YouTubeEmbed from "$lib/YouTubeEmbed.svelte";

  import rawMarkdown from "./video.md?raw";

  const videoId = "YgYKKCmcE04";
  const title = "Agentic Product Development - Erlend Sogge Heggen";
</script>

<div class="container">
  <div class="construction-icon">
    <img src="/construction-icon.svg" alt="Construction icon" />
  </div>
  <div class="markdown">
    <Markdown {rawMarkdown} />
  </div>
  <!-- <YouTubeEmbed {videoId} {title} /> -->
</div>

<style>
  .container {
    display: flex;
    flex-wrap: wrap;
    align-items: start;
    justify-content: center;
    gap: 5em;
    margin-top: 5em;
    padding-bottom: 6em;
  }

  .construction-icon {
    width: 20em;
  }

  .markdown {
    flex-basis: 40em;
    flex-grow: 1;
    text-underline-offset: 0.5em;
  }
</style>

<script>
  import Markdown from "$lib/Markdown.svelte";
  import rawMarkdown from "./video.md?raw";

  const videoTitle = "Agentic Product Development - Erlend Sogge Heggen";
  const videoSrc = "https://www.youtube-nocookie.com/embed/YgYKKCmcE04";
</script>

<div class="container video-container">
  <Markdown {rawMarkdown} />

  <iframe src={videoSrc} title={videoTitle} loading="lazy" allowfullscreen
  ></iframe>
</div>

<style>
  .video-container {
    --apect-ratio: 16 / 9;

    padding-top: 12em;
    padding-bottom: 6em;

    iframe {
      width: 1200px;
      max-width: 100%;
      max-height: 85vh;
      aspect-ratio: var(--apect-ratio);
      border-radius: var(--border-radius);
      box-shadow: 0px 5px 20px rgba(0, 0, 0, 0.5);
      margin-top: 5em;
      border: 0;
    }
  }
</style>

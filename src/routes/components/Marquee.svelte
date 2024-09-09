<script>
  import Markdown from "$lib/Markdown.svelte";
  import rawMarkdown from "./marquee/content.md?raw";
</script>

<section class="marquee">
  <div class="content">
    <Markdown {rawMarkdown} />
  </div>
</section>

<style>
  .marquee {
    --animation-speed: 30s;

    white-space: nowrap;
    min-height: 5em;
    background: #fff5bf;
    display: grid;
    place-items: center;
    font-weight: 700;
    position: relative;
    overflow: hidden;

    .content {
      color: #240940;
      position: absolute;

      animation: marquee var(--animation-speed) linear infinite;

      /* cooked markdown styles so we need :global */
      :global(p) {
        display: inline-block;
        margin: 0 2em;
        font-size: 1.5em;
      }
    }
  }

  @keyframes marquee {
    /* extend a bit more than the viewport to make it smooth */
    0% {
      transform: translateX(75%);
    }
    100% {
      transform: translateX(-75%);
    }
  }
</style>

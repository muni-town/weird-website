<script>
  import { marked } from "marked";
  export let rawMarkdown;
</script>

<div class="markdown-content">
  {@html marked(rawMarkdown)}
</div>

<style>
  .markdown-content {
    /* these are styles for cooked markdown
       without :global they get purged
    */

    :global(h3) {
      font-size: 3.5em;
      margin-bottom: 1em;
    }

    :global(p) {
      margin-bottom: 1.5em;
      font-size: 2em;
    }

    :global(a) {
      color: currentColor;
    }

    :global(ul) {
      font-size: 2em;
      margin-bottom: 1.5em;
      padding-left: 1em;
      list-style-type: disc;

      :global(li) {
        margin-bottom: 0.5em;
      }
    }
  }
</style>

<script>
  import Markdown from "$lib/Markdown.svelte";
  export let heading;
  export let description;
  export let rawMarkdown;
</script>

<div class="container">
  <div class="title">
    <h1>{heading}</h1>
    <p>{description}</p>
  </div>
  <div class="content">
    <Markdown {rawMarkdown} />
  </div>
</div>

<style>
  .container {
    color: white;
    padding-bottom: 15em;
    .title {
      display: grid;
      grid-template-columns: 0.4fr auto;
      padding: 2em;
      place-items: center;
      gap: 2em;
      h1 {
        font-family: "Rubik Mono One", monospace;
        font-size: 3.25em;
        margin: 0;
        width: 400px;
        line-height: 1.5;
        letter-spacing: 0.5px;
        user-select: none;
      }
      p {
        font-size: 2em;
        margin: 0;
        line-height: 1.5;
      }
      @media (max-width: 1200px) {
        grid-template-columns: 1fr;
        h1 {
          font-size: 2.5em;
          width: 100%;
        }
        p {
          font-size: 1.5em;
        }
      }
    }
    .content {
      margin: 8em 0 12em 0;
      background: #683481;
      padding: 5em 8em;
      border-radius: var(--border-radius);
      border: 2px solid black;
    }
  }
</style>

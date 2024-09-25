<script>
  import { onMount } from "svelte";
  import GithubIcon from "./icons/github.svelte";

  export let repository = "";

  let count = "";

  // TODO: this needs to run at build time
  onMount(async () => {
    const response = await fetch(`https://api.github.com/repos/${repository}`);
    const data = await response.json();
    count = data.stargazers_count;
  });
</script>

<a
  href={`https://github.com/${repository}`}
  target="_blank"
  rel="noopener noreferrer"
  class="github-star-button"
  aria-label="Star on GitHub"
>
  <span class="text"><GithubIcon /> Star</span>
  <span class="count">{count}</span>
</a>

<style>
  /* these match the GitHub button styles */
  .github-star-button {
    color: #25292e;
    background: #ebf0f4;
    border: 1px solid #d1d9e0;
    border-radius: 3px;
    text-decoration: none;
    padding: 0.25em;
    display: grid;
    grid-auto-flow: column;
    gap: 0.5em;
    place-items: center;
    font-size: 0.9em;
    display: grid;
    font-family: system-ui;
    min-height: 20px;
    font-weight: 600;

    .text {
      color: #25292e;
      display: grid;
      gap: 0.25em;
      grid-auto-flow: column;
      place-items: center;
      padding: 0 0.25em;

      &:hover {
        background-position: 0 -0.5em;
        background: linear-gradient(180deg, #eff2f5, #e5eaee 90%);
        border-color: #d1d9e0;
      }
    }

    .count {
      padding: 0 0.25em;

      border-left: 1px solid #d1d9e0;

      &:hover {
        color: #0969da;
      }
    }

    :global(svg) {
      fill: #25292e;
      height: 1.25em;
      width: 1.25em;
    }
  }

  .github-star-button span {
    font-size: 1.25em;
  }
</style>

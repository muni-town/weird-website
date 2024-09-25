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
  <GithubIcon />
  <span class="count">{count}</span>
</a>

<style>
  /* these match the GitHub button styles */
  .github-star-button {
    text-decoration: none;
    grid-auto-flow: column;
    gap: 1em;
    place-items: center;
    display: grid;
    font-family: system-ui;
    min-height: 20px;
    font-weight: 600;

    .count {
      color: white;
      min-width: 2ch;

      &:hover,
      &:focus,
      &:active {
        color: white;
      }
    }

    :global(svg) {
      fill: white;
      height: 2em;
    }
  }
</style>

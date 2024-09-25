<script>
  import GithubBadge from "./GithubBadge.svelte";

  const siteName = "Weird";

  const githubRepository = "muni-town/weird";

  const menuLinks = [{ text: "App", url: "https://a.weird.one" }];
</script>

<div class="header">
  <div class="container">
    <div class="logo">
      <a href="/">
        {siteName}
      </a>
    </div>
    <div class="menu">
      <ul>
        {#each menuLinks as { text, url }}
          <li>
            <a href={url}>
              {text}
            </a>
          </li>
        {/each}

        <li>
          <GithubBadge repository={githubRepository} />
        </li>
      </ul>
    </div>
  </div>
</div>

<style>
  .container {
    display: grid;
    grid-template-columns: 1fr auto;
  }

  .logo {
    a {
      color: #fff5bf;
      font-family: "Rubik Mono One", monospace;
      text-decoration: none;
      font-size: 1.75em;
      letter-spacing: 1px;
    }
  }

  .menu {
    display: grid;
    place-items: center;

    ul {
      display: grid;
      grid-auto-flow: column;
      gap: 2em;

      li {
        cursor: pointer;
        border-radius: var(--border-radius);
        padding: 0.5em;
        &:hover {
          background: rgba(255, 255, 255, 0.5);
        }
      }

      a {
        color: white;
        text-decoration: none;
        font-weight: 700;
        font-size: 1.6em;
      }
    }
  }
</style>

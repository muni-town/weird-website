<script>
  import GithubBadge from "./GithubBadge.svelte";

  const siteName = "Roomy";

  const githubRepository = "muni-town/roomy";

  const menuLinks = [{ text: "App", url: "https://roomy.space" }];
</script>

<header class="header">
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
</header>

<style>
  header {
    width: 100%;
  }
  .container {
    display: grid;
    align-items: center;
    grid-template-columns: 1fr auto;
    padding: 2rem 4vw;
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

<script>
  import GithubBadge from "./GithubBadge.svelte";

  const githubRepository = "muni-town/roomy";

  const menuLinks = [{ text: "Open App", url: "https://roomy.space", cta: true }];
</script>

<header class="header">
  <div class="container">
    <div class="menu">
      <ul>
        <li>
          <GithubBadge repository={githubRepository} />
        </li>

        {#each menuLinks as { text, url, cta }}
          <li class:cta-button={cta}>
            <a href={url} class:cta={cta}>
              {text}
            </a>
          </li>
        {/each}
      </ul>
    </div>
  </div>
</header>

<style>
  header {
    width: 100%;
  }
  .container {
    display: flex;
    justify-content: flex-end;
    padding: 2rem 4vw;
  }

  .logo {
    a {
      color: #fff5bf;
      font-family: "Hanken Grotesk", system-ui, sans-serif;
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
      gap: 0.5em;
      align-items: center;

      li {
        cursor: pointer;
        border-radius: var(--border-radius);
        padding: 0.5em;
        &:hover {
          background: rgba(255, 255, 255, 0.5);
        }
      }

      li.cta-button {
        padding: 0.5em;
        &:hover {
          background: none;
        }
      }

      a {
        color: white;
        text-decoration: none;
        font-weight: 700;
        font-size: 1.6em;
      }

      a.cta {
        color: oklch(98% 0.01 344);
        background: oklch(59.2% 0.249 1);
        border: 1px solid oklch(59.2% 0.249 1);
        border-radius: 10px;
        padding: 0.5em 1.2em;
        font-weight: 600;
        font-size: 1.4em;
        backdrop-filter: blur(12px);
        transition: transform 300ms, box-shadow 300ms;
      }

      a.cta:hover {
        box-shadow: 2px 2px 0 0 oklch(42.3% 0.166 15);
        transform: scale(1.01);
      }

      a.cta:active {
        transform: translateY(2px);
        box-shadow: none;
      }
    }
  }
</style>

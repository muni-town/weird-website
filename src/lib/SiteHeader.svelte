<script>
  const siteName = "Weird";

  const menuLinks = [
    { text: "Members", url: "https://weird.one/members" },
    { text: "Profile", url: "https://weird.one/auth/v1/account" },
    { text: "Register", url: "https://weird.one/auth/v1/users/register" },
  ];
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
      </ul>
    </div>
  </div>
</div>

<style>
  .header {
    padding: 0.75em;
  }

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
      gap: 4em;

      a {
        color: white;
        text-decoration: none;
        font-weight: 700;
        font-size: 1.6em;
      }
    }
  }
</style>

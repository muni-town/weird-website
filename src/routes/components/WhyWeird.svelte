<script>
  const title = "Further Reading";

  const links = [
    {
      text: "Magic website creator",
      url: "https://blog.erlend.sh/weird-web-pages",
    },
    {
      text: "Web Passports",
      url: "https://blog.erlend.sh/weird-netizens",
    },
    {
      text: "Further reading (for the nerds)",
      url: "https://blog.commune.sh/weird-happenings/",
    },
  ];
</script>

<section class="why-weird">
  <div class="container">
    <div class="image">
      <img
        alt="hand pointing"
        loading="lazy"
        src="/magic-hand.svg"
        height="300"
      />
    </div>

    <div class="content">
      <h3>{title}</h3>
      <ul>
        {#each links as { text, url }}
          <li>
            <a href={url}>
              <span class="link-text">{text}</span>
              <span
                class="link-arrow
                ">➜</span
              >
            </a>
          </li>
        {/each}
      </ul>
    </div>
  </div>
</section>

<style lang="scss">
  .why-weird {
    background: linear-gradient(180deg, #240940 40%, #8e4569);
    color: white;
    padding-bottom: 8em;
  }

  .container {
    display: grid;
    grid-template-columns: 35% 1fr;
    justify-content: end;
    padding-top: 12em;
    gap: 6em;
  }

  .image {
    display: grid;
    place-items: center;

    & img {
      width: 300px;
      height: auto;
      max-width: 100%;
    }
  }

  @media (max-width: 800px) {
    .container {
      grid-template-columns: 1fr;
    }

    .image {
      display: none;
    }
  }

  h3 {
    font-family: "uncutsans";
    font-size: 3.5em;
    margin: 0 0 0.75em 0;
  }

  p {
    font-size: 2em;
    margin: 0 0 1.5em;
  }

  ul {
    width: 350px;
    margin-top: 4.5em;
  }

  li {
    background: #b0a7e9;
    border: 2px solid currentColor;
    margin: 1.5em 0;
    color: black;
  }

  a {
    color: currentColor;
    text-decoration: none;
    display: grid;
    grid-auto-flow: column;
    place-items: stretch;
    height: 3em;
    grid-template-columns: 1fr 50px;
    font-size: 1.6em;

    & .link-text {
      display: grid;
      place-items: center self-start;
      padding-left: 1.5em;
    }

    & .link-arrow {
      display: grid;
      border-left: 2px solid currentColor;
      place-items: center;
    }
  }
</style>

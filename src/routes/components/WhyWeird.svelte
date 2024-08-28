<script>
  const sectionHeading = "Further Reading";
  const sectionSubheading = "for the nerds";

  const ProductLinksHeading = "Product";
  const ProductLinks = [
    {
      text: "Magic website creator",
      url: "https://blog.erlend.sh/weird-web-pages",
    },
    {
      text: "Web Passports",
      url: "https://blog.erlend.sh/weird-netizens",
    },
    {
      text: "Weird Happenings",
      url: "https://blog.commune.sh/weird-happenings/",
    },
  ];

  const protocolLinksHeading = "Protocols";
  const protocolLinks = [
    {
      text: "How to Federate?",
      url: "https://zicklag.katharos.group/blog/how-to-federate/",
    },
    {
      text: "A Web of Data",
      url: "https://zicklag.katharos.group/blog/a-web-of-data/",
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
      <h3>{sectionHeading}</h3>
      <h4>{sectionSubheading}</h4>

      <div class="link-list">
        <h5>{ProductLinksHeading}</h5>
        <ul>
          {#each ProductLinks as { text, url }}
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

      <div class="link-list">
        <h5>{protocolLinksHeading}</h5>
        <ul>
          {#each protocolLinks as { text, url }}
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

  .link-list {
    margin-bottom: 4em;
  }

  h3 {
    font-size: 3.5em;
    margin-bottom: 0.25em;
  }

  h4 {
    font-size: 1.25em;
    margin-bottom: 3em;
  }

  h5 {
    font-size: 1.5em;
    margin-bottom: 1.25em;
  }

  ul {
    width: 350px;
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

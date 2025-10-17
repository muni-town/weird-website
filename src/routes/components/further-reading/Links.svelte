<script>
  const sectionHeading = "Further Reading";
  const sectionSubheading = "for the nerds";
  const sections = [
    {
      heading: "Design & Philosophy",
      links: [
        {
          text: "A Brief History of Roomy's Architectures",
          url: "https://blog.muni.town/brief-history-of-roomy-architectures/",
        },
        {
          text: "ATProto Isn't What You Think",
          url: "https://blog.muni.town/atproto-isnt-what-you-think/",
        },
        {
          text: "Chatty Community Gardens",
          url: "https://blog.muni.town/chatty-community-gardens/",
        },
        {
          text: "Chat is minimum-viable anything",
          url: "https://blog.muni.town/chat-is-minimum-viable-anything/",
        },
      ],
    },
    {
      heading: "Releases",
      links: [
        {
          text: "Roomy Alpha 5",
          url: "https://blog.muni.town/roomy-space-alpha-5/",
        },
        {
          text: "Roomy Alpha 4",
          url: "https://blog.muni.town/roomy-space-alpha4/",
        },
        {
          text: "Roomy Alpha 3",
          url: "https://blog.muni.town/roomy-chat-alpha3/",
        },
        {
          text: "Roomy Alpha 2",
          url: "https://blog.muni.town/roomy-chat-alpha-2/",
        },
      ],
    },
    // {
    //   heading: "Protocol",
    //   links: [
    //     {
    //       text: "The Leaf Protocol",
    //       url: "https://zicklag.katharos.group/blog/introducing-leaf-protocol/",
    //     },
    //     {
    //       text: "How to Federate?",
    //       url: "https://zicklag.katharos.group/blog/how-to-federate/",
    //     },
    //     {
    //       text: "A Web of Data",
    //       url: "https://zicklag.katharos.group/blog/a-web-of-data/",
    //     },
    //     {
    //       text: "Leaf, ATProto and ActivityPub",
    //       url: "https://blog.muni.town/leaf-atproto-activitypub/",
    //     },
    //     {
    //       text: "Capabilities & Identity with Leaf",
    //       url: "https://blog.muni.town/capabilities-and-identity-with-leaf/",
    //     },
    //   ],
    // },
  ];
</script>

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
    <span class="section-subheading">{sectionSubheading}</span>
    {#each sections as { heading, links }}
      <div class="link-list">
        <span class="list-heading">{heading}</span>
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
    {/each}
  </div>
</div>

<style>
  .container {
    display: inline-grid;
    grid-template-columns: 1fr 1fr;

    gap: 7em;
    margin: 0 auto;

    @media (max-width: 800px) {
      grid-template-columns: 1fr;
    }
  }

  .image {
    display: grid;
    place-items: center;

    img {
      width: 300px;
      height: auto;
      max-width: 100%;
    }

    @media (max-width: 800px) {
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

  .section-subheading {
    font-size: 1.5em;
    margin-bottom: 3em;
    display: block;
  }

  .list-heading {
    font-size: 1.5em;
    margin-bottom: 1.25em;
    display: block;
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

    .link-text {
      display: grid;
      place-items: center self-start;
      padding-left: 1.5em;
    }

    .link-arrow {
      display: grid;
      border-left: 2px solid currentColor;
      place-items: center;
    }
  }
</style>

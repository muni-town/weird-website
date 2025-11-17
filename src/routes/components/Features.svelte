<script>
  const content = [
  {
    title: "Gardenable group chat that grows with you",
    text: [[
      "Every page, every thread, every post in Roomy is fundamentally a type of document. Any single chat message, discussion thread, or stand-alone page document can be transformed into the first draft of a Documentation Page, ",
      [
        "Digital Message Gardening",
        "https://blog.muni.town/chatty-community-gardens/"
      ]
    ]]
  },
  {
    title: "Communal resiliency",
    text: [[
      "Build sovereign communities, designed to persist under the harshest conditions with novelties like Universally Shared Records: you will have a local copy of your community's data at all times, and so will all your community members! ",
      [
        "Local-first software",
        "https://www.inkandswitch.com/essay/local-first/"
      ],
      " realizes ",
      [
        "Appropriate Technology",
        "https://en.wikipedia.org/wiki/Appropriate_technology"
      ]
    ]]
  },
  {
    title: "Peer powered",
    text: [[
      "Make communities that can, if necessary, endure purely on the shared resources of sufficiently aligned peers in a mutual-sharing network. ",
      [
        "Peer-2-Peer software",
        "https://en.wikipedia.org/wiki/Peer-to-peer"
      ]
    ]]
  },
  {
    title: "Public-first; privacy-friendly",
    text:[ `Roomy is designed first and foremost for publicly shared, collaborative content exchange. Priority conversations are carefully supported, but private spaces are not the primary use case for the platform.`,
      ` If you don't want your private group subjected to scrutiny, we will soon support self-hosting for full privacy.`]
  }
];
</script>

<section>
  <div class="container">
    <h2>Features</h2>

    <ul>
      {#each content as { title, text }}
        <li>
          <h3>{title}</h3>
            {#each text as p}
          <p>
            {#each p as t}
              {#if typeof t === "string"}
                {t}
              {:else}
                <a href={t[1]}>{t[0]}</a>
              {/if}
            {/each}
          </p>
            {/each}
        </li>
      {/each}
    </ul>
  </div>
</section>

<style>
  .container {
    background: var(--purple);
  }
  ul {
    display: grid;
    grid-template-columns: repeat(2, minmax(300px, max-content));
    justify-content: center;
    column-gap: 2rem;
    row-gap: 4rem;
    @media (max-width: 768px) {
      grid-template-columns: 1fr;
    }
  }
  p{
    max-width: 60ch;
    padding-block-start: .75em;
    }
  p+p {
    padding-block-start: .25em;
  }
  a {
    color: inherit;
  }
  h2 {
    text-align: center;
    font-size: 3em;
    padding-block-end: 6rem;
  }
  h3 {
    font-size: 1.75em;
    
  }
</style>

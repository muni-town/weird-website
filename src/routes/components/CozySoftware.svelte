<script>
  import { onMount } from "svelte";
  const tabs = [
    {
      label: "Move to thread",
      src: "roomy-messages-to-thread.png",
      alt: "Roomy: moving messages into a thread",
    },
    {
      label: "Toggle channel view",
      src: "roomy-new-thread.png",
      alt: "Roomy: toggling the channel view",
    },
    {
      label: "Space-wide index",
      src: "roomy-space-index.png",
      alt: "Roomy: the space-wide index",
    },
  ];
  let activeTab = 0;
  let rotating = true;
  let timer;

  onMount(() => {
    timer = setInterval(() => {
      if (rotating) activeTab = (activeTab + 1) % tabs.length;
    }, 4000);
    return () => clearInterval(timer);
  });

  function selectTab(i) {
    activeTab = i;
    rotating = false;
    if (timer) clearInterval(timer);
  }
</script>

<section>
  <h2>What is Roomy?</h2>
  <div class="layout">
    <div class="narrative">
    <p class="lead">
      Roomy creates rooms of sociality. Digital places for friends and
      collaborators to hang out in.
    </p>

    <p>
      The most common such social space in the digitized world is the
      group chat. Group chat starts out something like this:
    </p>

    <figure class="ascii-art">
      <pre>
[space]    | /room (channel/thread)
# channels | ( ) person: ~~~~~~~
# here     | ( ) person: ~~ ~~~~
           | ~~ ~~~~?
           | ( ) person: ~~~ ~~
           | ~~~~ ~~~~~~~ ~~~
           | ~~ ~~~~ ~~~~~ ~~~~~</pre
      >
      <figcaption>— mIRC, circa 1995</figcaption>
    </figure>

    <p>That's roughly what group chat has looked like since the 90s.</p>

    <p>
      Roomy is a lot more than 'group chat', but we do believe group chat
      is <em>minimum viable everything</em>, as it's the best default
      foundation for greenfield community building and digital relationing.
    </p>

    <p>So to begin with, Roomy looks like this familiar shape:</p>

    <img
      src="roomy-chat-screenshot.png"
      alt="Screenshot of the Roomy chat app"
      class="screenshot"
    />

    <h3>In search of structure</h3>

    <p>
      The thing about group chat as we know it is that it isn't
      structure-seeking. The modern Discord is not meaningfully better than
      old-school IRC at knowledge-management.
    </p>

    <p>
      That is, plain group chat doesn't really concern itself with producing
      knowledge artifacts, it just wants to keep the conversation flowing.
    </p>

    <p>
      For groups and orgs engaged in knowledge work, conversation is only
      the beginning.
    </p>

    <img
      src="roomy-structure.png"
      alt="Roomy showing threaded structure beyond plain group chat"
      class="screenshot"
    />

    <p>
      When larger spaces of discourse complexify, Roomy's UI expands
      incrementally to hold that complexity in orderly fashion.
    </p>

    <div class="tabs" role="tablist">
      {#each tabs as tab, i}
        <button
          type="button"
          role="tab"
          aria-selected={activeTab === i}
          class:on={activeTab === i}
          on:click={() => selectTab(i)}
        >
          {tab.label}
        </button>
      {/each}
    </div>

    {#each tabs as tab, i}
      <img
        src={tab.src}
        alt={tab.alt}
        class="screenshot"
        class:hidden={activeTab !== i}
      />
    {/each}

    <p>
      The best in the biz right now are
      <a href="https://zulip.com">Zulip</a> and
      <a href="https://discourse.org">Discourse</a>. Zulip in particular is
      very functionally similar to Roomy as far as the chat-to-threads
      paradigm goes.
    </p>

    <p>
      Where Roomy differs is as an <em>atmospheric web application</em>. An
      app that is 'atmospheric' is adhering to the
      <a href="https://atproto.com">AT protocol</a>.
    </p>

    <h3>Welcome to the Atmosphere</h3>

    <p>
      This protocol does for social media accounts what we already have for
      our telephoning accounts. Your telephone account is held in your
      telephone number. You own that number, not the telecom company. If you
      don't like your telecom provider, you can switch.
    </p>

    <img
      src="atproto-telephone.png"
      alt="Diagram: the AT protocol's analogy to telephone numbers"
      class="screenshot"
    />

    <p class="label">
      AT protocol takes the structural power dynamics of social media from
      this:
    </p>

    <img
      src="atproto-from.png"
      alt="Diagram: centralized social media power dynamics"
      class="screenshot"
    />

    <p class="label">..to this:</p>

    <img
      src="atproto-to.png"
      alt="Diagram: atmospheric, decentralized social media power dynamics"
      class="screenshot"
    />

    <p>
      Facilitated by group management apps like Roomy, that means your
      community can be made up of a mosaic of different atmospheric apps,
      whilst all sharing the same login and membership list.
    </p>

    <figure>
      <img
        src="roomy-atmosphere.png"
        alt="Concept design for Roomy integrations control"
        class="screenshot"
      />
      <figcaption>Concept design for Roomy integrations control</figcaption>
    </figure>

    <div class="cta">
      <p class="cta-msg">
        Want to try it out and keep updated? Come hang out in the Roomy
        space.
      </p>
      <a class="cta-btn" href="https://roomy.space/did:plc:gnwy2zbm3hu4gfdawzxmpb2s">
        Open the Roomy space →
      </a>
    </div>
    </div>
  </div>
</section>

<style>
  section {
    background: var(--blue);
    padding: 4rem 2rem 8rem;
    color: white;
  }

  h2 {
    font-weight: 900;
    margin-bottom: 4rem;
    color: #fbbfb2;
    font-size: 4.8rem;
    padding: 0 4rem;
    text-shadow:
      -2px 2px 0 #000,
      -4px 4px 0 var(--orange);
  }

  .layout {
    max-width: 720px;
    margin: 0 auto;
  }

  .narrative {
    font-size: 1.1em;
    line-height: 1.7;
    font-weight: 300;
  }

  .cta {
    margin: 2.5rem auto 1rem;
    text-align: center;
    padding: 2.2rem 1.5rem;
    border-radius: 12px;
    background: color-mix(in oklch, oklch(1 0 0) 8%, transparent);
    border: 1px solid color-mix(in oklch, oklch(1 0 0) 18%, transparent);
  }

  .cta-msg {
    font-size: 1.25em;
    color: #fff;
    margin: 0 0 1.5rem;
    font-weight: 400;
  }

  .cta-btn {
    display: inline-block;
    color: oklch(98% 0.01 344);
    background: oklch(59.2% 0.249 1);
    border: 1px solid oklch(59.2% 0.249 1);
    border-radius: 10px;
    padding: 0.5em 1.2em;
    font-weight: 600;
    font-size: 1.4em;
    text-decoration: none;
    backdrop-filter: blur(12px);
    transition: transform 300ms, box-shadow 300ms;
  }

  .cta-btn:hover {
    box-shadow: 2px 2px 0 0 oklch(42.3% 0.166 15);
    transform: scale(1.01);
  }

  .cta-btn:active {
    transform: translateY(2px);
    box-shadow: none;
  }

  .lead {
    line-height: 1.5;
    font-weight: 500;
    color: #fbbfb2;
    padding-block-end: 0.5em;
  }

  p {
    padding-block-end: 1.5em;
  }

  .ascii-art {
    margin: 2rem auto;
    text-align: center;
  }

  .ascii-art pre {
    display: inline-block;
    text-align: left;
    background: oklch(0.18 0.02 300);
    color: oklch(0.85 0.08 150);
    padding: 1.5rem 2rem;
    border-radius: 8px;
    font-family: "Courier New", Courier, monospace;
    font-size: 0.85em;
    line-height: 1.5;
    border: 1px solid oklch(0.3 0.04 300);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
    white-space: pre;
    overflow-x: auto;
  }

  .ascii-art figcaption {
    margin-top: 0.5rem;
    font-size: 0.8em;
    color: color-mix(in oklch, oklch(1 0 0) 70%, var(--blue));
    font-style: italic;
  }

  .screenshot {
    display: block;
    max-width: 100%;
    margin: 1rem auto 3rem;
    border-radius: 6px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.4);
    border: 1px solid oklch(0.3 0.04 300);
  }

  .tabs {
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem;
    padding: 0 0 0.4em;
    margin: 0;
  }

  .tabs button {
    background: color-mix(in oklch, oklch(1 0 0) 12%, transparent);
    border: 1px solid color-mix(in oklch, oklch(1 0 0) 25%, transparent);
    color: #fbbfb2;
    padding: 0.4rem 0.9rem;
    border-radius: 999px;
    font-weight: 500;
    font-size: 0.95em;
    font-family: inherit;
    cursor: pointer;
  }

  .tabs button:hover {
    background: color-mix(in oklch, oklch(1 0 0) 18%, transparent);
  }

  .tabs button.on {
    background: #fbbfb2;
    color: #240940;
    border-color: #fbbfb2;
  }

  .screenshot.hidden {
    display: none;
  }

  figcaption {
    text-align: center;
    font-size: 1.1em;
    color: color-mix(in oklch, oklch(1 0 0) 80%, transparent);
    margin: -1.5rem auto 2rem;
    font-style: italic;
  }

  .label {
    text-align: center;
    font-size: 1.15em;
    font-weight: 500;
    color: #fff;
    padding-block-end: 0.5em;
  }

  em {
    color: #fbbfb2;
    font-style: italic;
  }

  h3 {
    font-size: 1.6em;
    color: white;
    padding-block-end: 0.75em;
    padding-block-start: 1em;
  }

  a {
    color: #fbbfb2;
    text-decoration: underline;
    text-underline-offset: 2px;
  }

  @media (max-width: 768px) {
    h2 {
      font-size: 2.6em;
      padding: 0 1rem;
    }
  }
</style>

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

    <ul class="features">
      <li>Move to thread</li>
      <li>Toggle channel view</li>
      <li>Space-wide index</li>
    </ul>

    <img
      src="roomy-features.png"
      alt="Roomy UI features: move to thread, toggle channel view, space-wide index"
      class="screenshot"
    />

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

    <img
      src="roomy-mosaic.png"
      alt="A mosaic of different atmospheric apps sharing one login and membership"
      class="screenshot"
    />

    <img
      src="roomy-atmosphere.png"
      alt="Illustration of the atmospheric web of interconnected apps"
      class="screenshot"
    />
    </div>

    <p>
      The two best in the biz right now are
      <a href="https://zulip.com">Zulip</a> and
      <a href="https://discourse.org">Discourse</a>; Zulip in particular is
      very functionally similar to Roomy as far as the chat-to-threads
      paradigm goes.
    </p>

    <p>
      Where Roomy differs is as an <em>atmospheric web application</em>. An
      app that is "atmospheric" is one that adheres to the AT Protocol, or
      <em>atproto</em> for short.
    </p>

    <p>
      In short, it's a protocol that does for social media accounts what we
      already have for our telephone numbers. Your account is your telephone
      number. You own that number, not the telecom company. If you don't like
      your telephone company, you can switch.
    </p>

    <p class="cta">
      Community organizers can
      <a href="https://atproto.com">read more about atproto</a>.
    </p>
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
    margin: 2rem auto 3rem;
    border-radius: 6px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.4);
    border: 1px solid oklch(0.3 0.04 300);
  }

  .features {
    list-style: none;
    padding: 0 0 1.5em;
    margin: 0;
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem;
  }

  .features li {
    background: color-mix(in oklch, oklch(1 0 0) 12%, transparent);
    border: 1px solid color-mix(in oklch, oklch(1 0 0) 25%, transparent);
    color: #fbbfb2;
    padding: 0.4rem 0.9rem;
    border-radius: 999px;
    font-weight: 500;
    font-size: 0.95em;
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

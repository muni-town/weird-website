<section>
  <h2>What is Roomy</h2>
  <div class="narrative">
    <img src="/e6h.png" alt="bonfire illustration" class="bonfire" />

    <p class="lead">
      Roomy creates rooms of sociality. Digital places for friends and
      collaborators to hang out in.
    </p>

    <p>
      The most common such social space in the digitized world is the group
      chat.
    </p>

    <p>Group chat starts out something like this:</p>

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

    <p>
      That's what "group chat" has looked like since the 90s. Roomy is a lot
      more than that, but we do believe group chat is a
      <em>minimum viable product</em> — the best default foundation for
      greenfield community building and digital relations.
    </p>

    <p>So to begin with, Roomy looks like this:</p>

    <img
      src="screenshot-roomy-june-26.png"
      alt="Screenshot of Roomy app, June 2025"
      class="screenshot"
    />

    <p>
      The thing about group chat as we have it is that it isn't
      structure-seeking. The modern Discord is meaningfully better than IRC at
      knowledge-management, but it doesn't really concern itself with
      producing knowledge artifacts — it just wants to keep the conversation
      flowing.
    </p>

    <p>
      That's a great pursuit as far as it goes, but for groups and
      organizations in the business of knowledge worth, conversation is only
      the beginning.
    </p>

    <h3>Idea lifecycle</h3>

    <p>
      So when larger discourse spaces increase in complexity, Roomy's UI
      expands incrementally to hold that complexity.
    </p>

    <div class="ui-elements">
      <span class="ui-badge">index</span>
      <span class="ui-badge">toggle</span>
      <span class="ui-badge">more to thread</span>
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

  .narrative {
    max-width: 90ch;
    margin: 0 auto;
    font-size: 1.1em;
    line-height: 1.7;
    font-weight: 300;
  }

  .bonfire {
    display: block;
    width: min(50%, 800px);
    max-width: 360px;
    margin: 0 auto 3rem;
  }

  .lead {
    font-size: 1.25em;
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

  .ui-elements {
    display: flex;
    gap: 0.75rem;
    justify-content: center;
    padding-block: 1.5rem 2.5rem;
    flex-wrap: wrap;
  }

  .ui-badge {
    display: inline-block;
    background: oklch(0.25 0.06 300);
    color: oklch(0.85 0.06 280);
    padding: 0.4em 1em;
    border-radius: 6px;
    font-family: "Courier New", Courier, monospace;
    font-size: 0.85em;
    border: 1px solid oklch(0.35 0.06 290);
    letter-spacing: 0.02em;
  }

  .cta {
    padding-block-start: 1em;
    font-weight: 500;
  }

  a {
    color: #fbbfb2;
    text-decoration: underline;
    text-underline-offset: 2px;
  }

  .cta a {
    color: var(--orange);
    text-underline-offset: 3px;
  }

  @media (max-width: 768px) {
    .narrative {
      font-size: 1.1em;
    }
    .lead {
      font-size: 1.2em;
    }
    h2 {
      font-size: 2.6em;
      padding: 0 1rem;
    }
  }
</style>
<script>
  const content = [
    ["Safe", "moderated; incremental"],
    ["Accessible", "discoverable; user-friendly"],
    ["Casual", "default asynchronous; at-your-leisure"],
    ["Present", "optionally synchronous; in-the-moment"],
    ["Intimate", "selectively private/public; closeness by consent"],
  ];
</script>

<section>
  <h2>cozy community software</h2>
  <div>
    <img src="/e6h.png" alt="bonfire illustration" />
    <div class="text">
      <h3>
        Roomy is <a href="https://blog.erlend.sh/cozy-community-software"
          >designed to be</a
        >...
      </h3>
      <ul>
        {#each content as [head, body]}
          <li class="">
            <h4>{head}</h4>
            <p>{body}</p>
          </li>
        {/each}
      </ul>
    </div>
  </div>
</section>

<style>
  section {
    background: var(--blue);
    padding: 4rem 2rem;
    color: white;
  }

  h2 {
    font-weight: 900;
    margin-bottom: 6rem;
    color: #fbbfb2;
    font-size: 4.8rem;
    padding: 0 4rem;
    text-shadow:
      -2px 2px 0 #000,
      -4px 4px 0 var(--orange);
  }

  section > div {
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    gap: 3rem;

    @media (max-width: 968px) {
      flex-direction: column;
    }
  }

  img {
    width: min(50%, 800px);
  }

  h3 {
    font-size: 2.4rem;
    margin-bottom: 3rem;
    & > a {
      color: inherit;
      text-decoration: underline;
    }
  }

  ul {
    list-style: none;
  }

  li {
    padding-bottom: 1.5rem;
    color: color-mix(in oklch, oklch(1 0 0) 90%, var(--blue));
  }

  h4 {
    font-size: 1.8rem;
    padding-block-end: 0.4rem;
    font-weight: 500;
  }

  p {
    font-size: 1.6rem;
    line-height: 1.25;
  }
</style>

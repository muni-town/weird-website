<script>
  const preludeText = "just like milk and honey...";
  const heading = "Weird is a combination of two things that go together";

  const cards = [
    {
      icon: "➢",
      title: "Magic website creation",
      body: "The simplest possible way to create your own personal space on the web.",
    },
    {
      icon: "➣",
      title: "Self-sovereign internet passport",
      body: "Independent 'social sign-in' for the alt-web.",
    },
  ];
</script>

<section class="features">
  <div class="image">
    <img
      alt="Milk and honey"
      loading="lazy"
      height="350"
      src="/honeymilk.svg"
    />
  </div>
  <div class="container">
    <div>
      <span class="prelude">{preludeText}</span>
      <h2>{heading}</h2>
    </div>
    <div class="cards">
      {#each cards as { icon, title, body }}
        <div class="card">
          <div>
            <span class="icon">{icon}</span>
            <h3>{title}</h3>
            <p>{body}</p>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style lang="scss">
  .features {
    padding-bottom: 2em;
    background: linear-gradient(180deg, #fff5bf, #e47689);
    border-top: 2px solid black;
    display: grid;
  }

  .image {
    place-self: center;
    margin-top: -18em;
    margin-bottom: 2em;
    position: relative;

    & img {
      /* image size */
      width: 550px;
    }
  }

  .prelude {
    display: block;
    margin: 1em 0;
    font-weight: 700;
    font-size: 2em;
  }

  h2 {
    font-size: 4em;
    /* don't let the text get too wide */
    max-width: 550px;
  }

  .cards {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3em;
    margin-top: 4em;

    @media (max-width: 900px) {
      grid-template-columns: 1fr;
    }
  }

  .card {
    background: #9bafe1;
    padding: 3em 4em;
    border-radius: var(--border-radius);
    box-shadow: 0px 3px 0 5px black;
    position: relative;

    & .icon {
      font-size: 5em;
    }

    & h3 {
      font-size: 2.5em;
      margin: 1em 0;
    }

    & p {
      font-size: 1.75em;
    }
  }
</style>

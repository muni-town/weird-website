<script>
  import WebPasspostsCard from "./features/web-passports.svelte";
  import MagicWebsiteCreatorCard from "./features/magic-website-creator.svelte";

  const preludeText = "just like milk and honey...";
  const heading = "Weird is a combination of two things that go together";
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
      <MagicWebsiteCreatorCard />
      <WebPasspostsCard />
    </div>
  </div>
</section>

<style>
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

    img {
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
</style>

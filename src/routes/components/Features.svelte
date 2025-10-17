<script>
  import WebPasspostsCard from "./features/web-passports.svelte";
  import Features from './features/features.svelte'
  import MagicWebsiteCreatorCard from "./features/magic-website-creator.svelte";
  import AvailableToday from "./features/available-today.svelte";
  import ComingSoon from "./features/coming-soon.svelte";

  const preludeText = "just like milk and honey...";
  const heading = "Weird is a combination of two things that go together";
</script>

<!-- <section class="features"> -->
  <Features />
 <!-- <div class="container"> -->
<!--
    <h2>Your starter-pack for <a href="https://den.dev/blog/be-a-property-owner-not-a-renter-on-the-internet/">property-ownership on the internet</a></h2>
    <div class="cards">
      <AvailableToday />
      <ComingSoon />
    </div>
    -->
    <!-- <div class="milk-and-honey">
      <div class="text-block">
        <span class="prelude">{preludeText}</span>
        <h2>{heading}</h2>
      </div>
      <div class="image">
        <img
          alt="Milk and honey"
          loading="lazy"
          height="350"
          src="/honeymilk.svg"
        />
      </div>
    </div>
    <div class="cards">
      <MagicWebsiteCreatorCard />
      <WebPasspostsCard />
    </div>
  </div> -->
<!-- </section> -->

<style>
  .features {
    padding-bottom: 2em;
    background: linear-gradient(180deg, #fff5bf, #e47689);
    display: grid;
  }


  .milk-and-honey {
    height: 35em;
    display: flex;
    align-items: center;
    justify-content: space-between;

    .image {
      margin-top: -5em;
      margin-bottom: 2em;
      position: relative;

      img {
        /* image size */
        width: 550px;
      }
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

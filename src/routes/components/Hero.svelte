<script lang="ts">
  import SiteHeader from "$lib/SiteHeader.svelte";
</script>

<div class="stars"><img src="/stars.svg" alt="" /></div>
<section class="hero">
  <div class="header"><SiteHeader /></div>
  <div class="clouds"><img src="/cloud.svg" alt="" /></div>
  <div class="content">
    <div class="hero-copy">
      <div class="hero-title">
        <div class="hero-logo-masked" aria-hidden="true"></div>
        <h1>Roomy</h1>
      </div>
      <p class="subhead">
        make space <br /> cultivate knowledge
      </p>
    </div>
    <!-- <div class="image">
      <div class="full-size">
        <img alt="keyboard and monitor" height="450" src="/hero.svg" />
      </div>
      <div class="small-size">
        <img alt="keyboard" height="300" src="/keyboard.svg" />
        <img alt="monitor" height="200" src="/Screen.svg" />
      </div>
    </div> -->
  </div>
</section>

<style>
  section {
    display: grid;
    position: relative;
    grid-template-rows: min-content 1fr;
    justify-items: center;
    max-width: 100%;
    background: #2F2F2C;
    & > div {
      width: 100%;
      grid-column: 1/1;
      grid-row: 2/-1;
    }
    .header {
      grid-column: 1/1;
      grid-row: 1/1;
      z-index: 1;
    }
  }
  .stars {
    opacity: 0;
    position: absolute;
    z-index: 1;
    width: 100%;
    pointer-events: none;
    img {
      object-fit: cover;
      height: 80vh;
      width: 100%;
    }
    grid-column: 1/1;
    grid-row: 1/-1;
  }
  .clouds {
    display: none;
    position: absolute;
    bottom: 0px;
    left: 0;
    /* actual size of the image */
    width: 30vw;
  }

  .content {
    display: grid;
    padding-top: 2em;
    padding-bottom: 8em;
    justify-items: center;
    z-index: 1;
  }
  .hero-copy {
    text-align: center;

    .hero-title {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 2em;
    }

    .hero-logo-masked {
      height: min(24vw, 14em);
      width: auto;
      aspect-ratio: 124 / 161;
      margin-top: min(16vw, 10em);
      background: radial-gradient(ellipse 200% 100% at 40% 50%, white 0%, var(--yellow) 100%);
      mask: url(/roomy-logo.svg) center / contain no-repeat;
      -webkit-mask: url(/roomy-logo.svg) center / contain no-repeat;
    }

    h1 {
      font-family: "Hanken Grotesk", system-ui, sans-serif;
      font-weight: 900;
      font-size: min(16vw, 8em);
      letter-spacing: -0.05em;
      background: radial-gradient(ellipse 200% 100% at 40% 50%, white 0%, var(--yellow) 100%);
      background-clip: text;
      -webkit-text-fill-color: transparent;
      padding: 0 0.5em 0 0;
    }

    .subhead {
        font-weight: 500;
        margin: -2em 0 3em auto;
        max-width: 10em;
        text-align: right;
    }

    p {
      color: white;
      font-weight: 700;
      font-size: 3em;

      @media (max-width: 1200px) {
        font-size: 2.5em;
      }

      @media (max-width: 800px) {
        font-size: 2em;
      }

      @media (max-width: 700px) {
        font-size: 1.5em;
      }
    }
  }

  .image {
    padding-inline: 9rem;
    width: 100%;
    max-height: 300px;
    max-width: 1200px;

    .small-size {
      display: none;
    }
    .full-size {
      margin-block-start: -50px;
      margin-block-end: -100px;
    }

    @media (max-width: 800px) {
      .small-size {
        display: grid;
        grid-auto-flow: column;
        place-items: center;
        gap: 2em;
      }
      .full-size {
        display: none;
      }
    }
  }
</style>

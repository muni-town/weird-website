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
        <div class="hero-logo-wrap">
          <div class="hero-logo-glow" aria-hidden="true">
            <svg width="124" height="161" viewBox="0 0 124 161" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M0.89114 52.5148C5.74879 8.5145 50.7373 -0.91772 81.2964 0.0675208C131.191 1.67688 123.884 108.194 121.289 147.779C113.639 153.593 105.664 157.579 97.5777 160.238C98.5486 126.744 106.51 26.7415 65.0982 17.8761C-25.1882 2.15781 11.6956 106.588 13.7154 158.802C12.1171 158.374 10.5156 157.909 8.91458 157.404C6.13105 124.579 -2.83023 86.2244 0.89114 52.5148Z" fill="currentColor"/>
              <path d="M86.187 90.826C89.2356 81.4371 80.4693 73.6875 73.4013 78.2469C61.1191 86.1699 81.9066 104.008 86.187 90.826Z" fill="currentColor"/>
            </svg>
          </div>
          <div class="hero-logo-masked" aria-hidden="true"></div>
        </div>
        <h1>Roomy</h1>
      </div>
      <div class="bubbles">
        <div class="bubble bubble-make">
          <span>make space</span>
        </div>
        <div class="bubble bubble-cultivate">
          <span>cultivate knowledge</span>
        </div>
      </div>
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
    background: linear-gradient(180deg, #2F2F2C 0%, #1A1A18 100%);
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
    padding-bottom: 18em;
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

    .hero-logo-wrap {
      position: relative;
      height: min(24vw, 14em);
      aspect-ratio: 124 / 161;
      margin-top: min(16vw, 10em);
    }

    .hero-logo-masked {
      width: 100%;
      height: 100%;
      background: radial-gradient(ellipse 200% 100% at 40% 50%, white 0%, var(--yellow) 100%);
      mask: url(/roomy-logo.svg) center / contain no-repeat;
      -webkit-mask: url(/roomy-logo.svg) center / contain no-repeat;
    }

    .hero-logo-glow {
      position: absolute;
      inset: -0%;
      color: var(--yellow);
      opacity: 70%;
      filter: blur(24px);
      z-index: -1;
      display: flex;
      align-items: center;
      justify-content: center;
      animation: glow-pulse 4s ease-in-out infinite;
      transition: opacity 0.3s ease, transform 0.3s ease;

      svg {
        width: 100%;
        height: 100%;
      }
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

    .bubbles {
      display: flex;
      flex-direction: column;
      align-items: flex-end;
      gap: 0;
      margin: -2em -3em 3em auto;
      max-width: 24em;
      position: relative;

      @media (max-width: 700px) {
          max-width: 20em;
      }
    }

    .bubble {
      border-radius: 2em;
      padding: 0.4em 1.2em;
      font-weight: 400;
      font-size: 1.8em;
      position: relative;
      width: fit-content;
      line-height: 1.4;
      border: 1px solid #4A4A47;
      white-space: nowrap;
      transition: background 0.3s ease;

      &:hover {
        background: #3A3A37;
      }

      @media (max-width: 1200px) {
        font-size: 1.6em;
      }

      @media (max-width: 800px) {
        font-size: 1.4em;
      }

      @media (max-width: 700px) {
        font-size: 1.3em;
      }
    }

    section:hover .hero-logo-glow {
      opacity: 90% !important;
      transform: scale(1.12);
    }

    .bubble-make {
      background: #2F2F2C;
      color: white;
      align-self: flex-end;
      margin-bottom: -0.3em;
      margin-left: 2em;
      z-index: 2;
      animation: float 7.5s ease-in-out infinite;
    }

    .bubble-cultivate {
      background: #2F2F2C;
      color: white;
      align-self: flex-start;
      z-index: 1;
      animation: float 7.5s ease-in-out infinite;
      animation-delay: -1.25s;
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

  @keyframes float {
    0%, 100% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-3px);
    }
  }

  @keyframes glow-pulse {
    0%, 100% {
      opacity: 50%;
      transform: scale(1);
    }
    50% {
      opacity: 80%;
      transform: scale(1.08);
    }
  }
</style>

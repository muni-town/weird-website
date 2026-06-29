<section>
  <div class="container">
    <picture>
      <source
        srcset="screenshot-roomy-june-29.png"
        media="(min-width: 769px)"
      />
      <img
        src="screenshot-roomy-june-29-mobile.png"
        alt="Screenshot of Roomy app, June 2025."
        class="screenshot"
      />
    </picture>
    <div class="new-thing">
      <p>
        Roomy is a freeform communications playground for messages both big and
        small, fast and slow; in these roomy spaces we move together at the
        speed of understanding.
      </p>
    </div>
  </div>
</section>

<style>
  section {
    text-align: center;
    background: linear-gradient(
      180deg,
      var(--yellow),
      oklch(69.71% 0.1361 10.71)
    );
  }

  .screenshot {
    @media (width > 900px) {
      max-width: 80%;
    }
    @media (width <= 768px) {
      width: 80%;
      aspect-ratio: 1290 / 2096.25;
      object-fit: cover;
      object-position: top;
    }
    position: relative;
    z-index: 2;
    margin-top: -18em;
    box-shadow: 0px 3px 0 5px black;
    border-radius: 5px;
  }

  .new-thing {
    --main-width: 64rem;
    max-width: var(--main-width);
    margin-inline: auto;
    padding-block-end: 2rem;
    p {
      padding-block: 2rem;
    }
  }
</style>

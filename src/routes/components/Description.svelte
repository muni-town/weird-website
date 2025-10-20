<section>
  <div class="first container"></div>
  <div class="second container">
    <img
      src="screenshot1.webp"
      alt="Screenshot of Roomy app."
      class="screenshot"
    />
    <div class="new-thing">
      <p>
        Roomy is a freeform communications playground for messages both big and
        small, fast and slow; in these roomy spaces we move together at the
        speed of understanding.
      </p>
      <div class="border"></div>
    </div>
  </div>
</section>

<style>
  :root {
    --offset: 200px;
  }
  section {
    text-align: center;
  }
  .first {
    background: linear-gradient(180deg, var(--p2), var(--p3), var(--p4));
    padding-block-end: var(--offset);
  }
.second {
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
    .border {
      border-top: 1px solid black;
      height: 1px;
      max-width: calc(var(--main-width) - 10rem);
      margin-inline: auto;
      width: 100%;
    }
  }
</style>

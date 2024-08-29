<script>
  const marqueeText = "Say hello, again, to the weird web.";

  // repeat the string for a smooth marquee effect
  const emptyArr = Array.from({ length: 3 });
</script>

<section class="marquee">
  <div class="content">
    {#each emptyArr as _}
      <span>{marqueeText}</span>
    {/each}
  </div>
</section>

<style>
  .marquee {
    white-space: nowrap;
    overflow: hidden;
    position: relative;
    min-height: 5em;
    background: #fff5bf;
    display: grid;
    place-items: center;

    .content {
      font-family: "Space Mono", monospace;
      color: #240940;
      display: inline-grid;
      align-items: center;
      grid-template-columns: 1fr 1fr 1fr;
      gap: 4em;
      font-size: 1.5em;
      position: absolute;
      font-weight: 700;
      animation: marquee 25s linear infinite;
    }
  }

  @keyframes marquee {
    /* extend a bit more than the viewport to make it smooth */
    0% {
      left: 110%;
    }
    100% {
      left: -110%;
    }
  }
</style>

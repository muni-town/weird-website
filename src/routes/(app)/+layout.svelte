<script>
  import SiteHeader from "$lib/SiteHeader.svelte";
</script>

<SiteHeader />
<div class="stars"></div>
<main>
  <slot />
</main>

<style>
  :global(body) {
    background: linear-gradient(180deg, #250941 25%, #de7287);
    min-height: 100vh;
  }
  .stars {
    background: url("/stars.avif");
    height: 40vh;
    width: 100%;
    background-position: center;
    position: absolute;
    left: 0;
    top: 0;
    z-index: -1;
  }
</style>

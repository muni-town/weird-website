<script>
  import SiteHeader from "$lib/SiteHeader.svelte";
  import Hero from "./components/Hero.svelte";
  import Description from "./components/Description.svelte";
  import Features from "./components/Features.svelte";
  import Marquee from "./components/Marquee.svelte";
  import FurtherReading from "./components/FurtherReading.svelte";
  import SiteFooter from "$lib/SiteFooter.svelte";
</script>

<SiteHeader />
<Hero />
<Description />
<Features />
<Marquee />
<FurtherReading />
<SiteFooter />

<style>
  :global(body) {
    background: linear-gradient(180deg, #250941 20%, #de7287 40%);
    background-repeat: no-repeat;
    background-size: cover;
  }

  :global(.italicize) {
    font-style: italic;
  }
</style>

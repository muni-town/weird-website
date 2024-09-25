<script>
  export let videoId = "";
  export let title = "";
  export let playerFeatures = ["autoplay"];

  const thumbnailUrl = `https://img.youtube.com/vi/${videoId}/maxresdefault.jpg`;
  const iframeSrc = `https://www.youtube.com/embed/${videoId}?autoplay=1`;

  let showIframe = false;

  const onThumbnailClick = () => {
    showIframe = true;
  };
</script>

<div class="youtube-embed">
  {#if showIframe}
    <iframe
      src={iframeSrc}
      allowfullscreen
      {title}
      allow={playerFeatures.join(" ")}
    ></iframe>
  {:else}
    <div
      class="thumbnail"
      role="button"
      tabindex="0"
      on:click={onThumbnailClick}
      on:keydown={(event) => {
        if (event.key === "Enter") onThumbnailClick();
      }}
    >
      <img src={thumbnailUrl} alt={title} loading="lazy" />
      <div class="play-button">
        <svg viewBox="0 0 24 24" fill="white">
          <path d="M8 5v14l11-7z" />
        </svg>
      </div>
    </div>
  {/if}
</div>

<style>
  .youtube-embed {
    --apect-ratio: 16 / 9;

    .thumbnail {
      position: relative;
      cursor: pointer;

      .play-button {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        background-color: rgba(0, 0, 0, 0.7);
        border-radius: 50%;
        width: 60px;
        height: 60px;
        display: flex;
        align-items: center;
        justify-content: center;

        svg {
          width: 30px;
          height: 30px;
        }
      }
    }

    img,
    iframe {
      width: 1200px;
      max-width: 100%;
      max-height: 85vh;
      aspect-ratio: var(--apect-ratio);
      border-radius: var(--border-radius);
      box-shadow: 0 5px 20px #00000080;
      margin-top: 5em;
      border: 0;
      object-fit: cover;
    }
  }
</style>

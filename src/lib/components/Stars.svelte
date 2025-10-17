<script lang="ts">
  import { onMount } from "svelte";
  const MIN = 0.8;
  const MAX = 3;
  let w = $state(0);
  let h = $state(0);
  /** oklch Hue values*/
  let hues = [95, 143, 208, 234, 241, 249, 61, 64, 69, 81];

  type Star = {
    x: number;
    y: number;
    r: number;
    hue: number;
    delta: number;
  };

  let noJs = $state(true);
  let dpr: number = $state(0);
  let animationFrameId: number = 0;

  onMount(() => {
    dpr = window.devicePixelRatio;
    noJs = false;

    return () => {
      if (animationFrameId) {
        cancelAnimationFrame(animationFrameId);
      }
    };
  });

  function randomColor() {
    return hues[Math.floor(Math.random() * 10)];
  }

  const twinkle = (canvas: HTMLCanvasElement) => {
    let ctx = canvas.getContext("2d")!;
    if (!ctx) {
      return console.error("2D Context creation failed");
    }
    ctx.scale(dpr, dpr);
    ctx.imageSmoothingEnabled = true;
    ctx.imageSmoothingQuality = "medium";

    var stars: Star[] = new Array(800);
    for (let i = 0; i < stars.length; i++) {
      stars[i] = {
        x: Math.random(),
        y: Math.random(),
        r: Math.random() * 1.5 + 1,
        hue: randomColor(),
        delta: Math.random(),
      };
    }
    const fixedHeight = 1300 * .9
    const resizeCanvas = () => {
      if(window.innerWidth === canvas.width) return
      const rect = { width: window.innerWidth, height: fixedHeight };
      canvas.width = rect.width * dpr;
      canvas.height = rect.height * dpr;
      w = rect.width;
      h = rect.height;
      canvas.style.width = `${rect.width}px`;
      canvas.style.height = `${rect.height}px`;
    };
    resizeCanvas();

    const shiftDelta = (star: Star) => {
      star.r += 0.04 * star.delta;

      // Bounds check
      if (star.r > MAX) {
        star.r = MAX;
        star.delta = -Math.abs(star.delta);
      } else if (star.r < MIN) {
        star.r = MIN;
        star.delta = Math.abs(star.delta);
      }
    };

    const draw = (star: Star) => {
      const x = star.x * w;
      const y = star.y * h;
      const size = star.r * 1.5;
      ctx.beginPath();
      for (let i = 0; i < 4; i++) {
        const angle = (i * Math.PI) / 2;
        const outerX = x + Math.cos(angle) * size;
        const outerY = y + Math.sin(angle) * size;
        const innerX = x + Math.cos(angle + Math.PI / 4) * (size * 0.4);
        const innerY = y + Math.sin(angle + Math.PI / 4) * (size * 0.4);

        if (i === 0) ctx.moveTo(outerX, outerY);
        else ctx.lineTo(outerX, outerY);

        ctx.lineTo(innerX, innerY);
      }
      ctx.closePath();

      ctx.shadowBlur = 8;
      ctx.shadowColor = `oklch(.97 0.005 ${star.hue + 30})`;
      ctx.fillStyle = `oklch(.87 ${star.r * 0.006} ${star.hue} / ${star.r / MAX / 1.5})`;
      ctx.fill();
    };

    const FPS = 120;
    const FRAME_INTERVAL = 1000 / FPS;
    let last = 0;
    function animate() {
      if (animationFrameId - last > FRAME_INTERVAL) {
        last = animationFrameId;
        ctx.clearRect(0, 0, w, h);
        stars.forEach((s) => {
          shiftDelta(s);
          draw(s);
        });
      }
      if (window.matchMedia("(prefers-reduced-motion: reduce)").matches) return;
      animationFrameId = requestAnimationFrame(animate);
    }

    animate();

    window.addEventListener("resize", resizeCanvas);

    return {
      destroy() {
        window.removeEventListener("resize", resizeCanvas);
        if (animationFrameId) {
          cancelAnimationFrame(animationFrameId);
        }
      },
    };
  };
</script>

<svelte:window />
{#if noJs}
  <img src="/stars.svg" alt="" />
{:else}
  <canvas use:twinkle></canvas>
{/if}

<style>
  img,
  canvas {
    object-fit: cover;
    width: 100%;
    height: 90vh;
  }
</style>

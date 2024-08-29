<div class="bottom-gradient">
  <div></div>
  <div></div>
</div>

<style>
  .bottom-gradient {
    --box-size: 40px;
    --lite-color: #9bafe1;
    --dark-color: #421558;
    --gradient-angle: 90deg;
    --gradient-stops: 50%;

    height: var(--box-size);
    background-size: calc(var(--box-size) * 2);

    div {
      height: var(--box-size);
      background-size: calc(var(--box-size) * 2);

      &:nth-child(1) {
        background-image: linear-gradient(
          var(--gradient-angle),
          var(--dark-color) var(--gradient-stops),
          var(--lite-color) var(--gradient-stops)
        );
      }

      &:nth-child(2) {
        background-image: linear-gradient(
          var(--gradient-angle),
          var(--lite-color) var(--gradient-stops),
          var(--dark-color) var(--gradient-stops)
        );
      }
    }
  }
</style>

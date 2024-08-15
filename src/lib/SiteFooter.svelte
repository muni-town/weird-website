<div class="bottom-gradient">
  <div></div>
  <div></div>
</div>

<style lang="scss">
  .bottom-gradient {
    --box-size: 40px;
    --lite-color: #9bafe1;
    --dark-color: #421558;

    height: var(--box-size);
    background-size: calc(var(--box-size) * 2);

    & div {
      height: var(--box-size);
      background-size: calc(var(--box-size) * 2);

      &:nth-child(1) {
        background-image: linear-gradient(
          90deg,
          var(--dark-color) 50%,
          var(--lite-color) 50%
        );
      }

      &:nth-child(2) {
        background-image: linear-gradient(
          90deg,
          var(--lite-color) 50%,
          var(--dark-color) 50%
        );
      }
    }
  }
</style>

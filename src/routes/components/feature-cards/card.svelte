<div class="card">
  <div>
    <span class="icon">
      <slot name="icon" />
    </span>
    <h3>
      <slot name="title" />
    </h3>
    <div class="body">
      <slot name="body" />
    </div>
  </div>
</div>

<style>
  .card {
    background: #9bafe1;
    padding: 3em 4em;
    border-radius: var(--border-radius);
    box-shadow: 0px 3px 0 5px black;
    position: relative;

    .icon {
      font-size: 5em;
    }

    h3 {
      font-size: 2.5em;
      margin: 1em 0;
    }
  }
</style>

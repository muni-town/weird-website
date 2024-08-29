<section class="description">
  <div class="container">
    <div class="content">
      <div class="card">
        <p>
          <span>The time has come to</span>
          <a href="https://webdirections.org/blog/reweirding-the-web/">
            reweird
          </a>
          <span>
            the web! We're doing our little part by making a prosocial network
            based on the cornerstone of the internet:
          </span><a
            href="https://blog.jim-nielsen.com/2022/other-peoples-websites/"
            >Personal websites</a
          >.
        </p>
      </div>
    </div>
  </div>
</section>

<style>
  .description {
    position: relative;

    &:before,
    &:after {
      content: "";
      background: url("/cloud.svg");
      background-repeat: no-repeat;
      position: absolute;
      z-index: -2;
      /* actual size of the image */
      height: 170px;
      width: 240px;
    }

    &:before {
      left: 0;
      /* pull the left cloud up */
      top: -30%;

      @media (max-width: 1200px) {
        top: 0;
      }
    }

    &:after {
      right: 0;
      /* push the right cloud down */
      top: 10%;
    }
  }

  .content {
    width: 900px;
    max-width: 100%;
    margin: 0 auto;
  }

  .card {
    background: #b0a7e9;
    padding: 6em 5em 20em 5em;
    border: 2px solid black;
    border-radius: var(--border-radius);
    position: relative;

    &:before {
      content: "";
      width: 100%;
      height: 100%;
      position: absolute;
      background: #b0a7e9;
      z-index: -1;
      right: -2.25em;
      top: -2.25em;
      border: 2px solid black;
      border-radius: var(--border-radius);
    }
  }

  p {
    font-weight: 700;
    font-style: normal;
    font-size: 2.25em;
  }

  a {
    color: black;
    font-weight: 700;
  }
</style>

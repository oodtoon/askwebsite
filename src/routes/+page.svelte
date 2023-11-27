<script lang="ts">
</script>

<div class="home-container">
  <img
    class="title-img"
    src="https://askpsychologicalservices.com/images/3cc98553e78333ece2ac284d66c46fbb.png"
    alt="ask-logo"
  />

  <h1 class="title">Your Journey Starts Here</h1>
  <div class="content">
    <p>
      When you are in need of help, the best thing you can do is to <a
        href="/contact">ASK</a
      >.
    </p>
    <p>
      Arianna, Samantha, and Karen are all highly trained psychologists and
      social workers that get you the help you need and moving in the right
      direction for you.
    </p>
    <p>
      Whether you need individual therapy, thrive in a group setting, or need an
      evaluation, we got you covered.
    </p>
    <p>Need help? Just <a href="/contact">ASK</a>. It's in our name.</p>
  </div>
</div>

<style>
  a {
    color: white;
  }

  .home-container {
    display: flex;
    flex-direction: column;
    gap: 4em;
    margin: 2em 4em;
    align-content: center;
    justify-content: center;
  }

  .title-img {
    margin: auto;
    max-width: 300px;
    box-shadow: var(--ask-shadow);
    border-radius: 50% 50% 0 0;
  }

  .title {
    margin: auto;
    color: var(--ask-purple);
  }

  .content {
    color: white;
    background-color: var(--ask-purple);
    font-size: 24px;
    padding: 2em;
    border-radius: 4px;
    text-align: center;
    box-shadow: var(--ask-shadow);
    max-width: 800px;
    margin: auto;
    position: relative;
  }

  .content::before {
    content: "";
    position: absolute;
    background: transparent;
    top: -30px;
    left: -30px;
    right: 30px;
    bottom: 20px;
    border: 10px solid white;
    pointer-events: none;
  }

  @media (max-width: 420px) {
    .home-container {
      margin: 2em 1em;
    }

    .title-img {
      width: 150px
    }

    .content { 
      padding: 0 1em 0 .5em;
    }

    .content::before {
      right: 10px;
      bottom: 10px;
    }
  }
</style>

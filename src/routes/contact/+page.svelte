<script lang="ts">
  import PageTitle from "$lib/components/PageTitle.svelte";
  import ContactTypes from "$lib/components/icons/ContactTypes.svelte";
  import team from "$lib/images/askTeamAlt.png";

  let outerWidth: number;

  let imgHolder =
    "https://askpsychologicalservices.com/images/d93bea1563a5721e4aa0bdbc0bb36799.png";
</script>

<svelte:window bind:outerWidth />

<div class="contact-container">
  <PageTitle title="CONTACT US" />

  <div class="content-container">
    <div class="img-container">
      <img src={team} alt="Alt team pic" />
    </div>
    <div class="info-container">
      <ContactTypes />
      <div class="info">
        We are eager to help!
        <br />
        Call or email us today!
      </div>
      <div class="info">
        85 MACOMB PLACE SUITE 102
        <br />
        MT. CLEMENS, MI 48043
        <br />
        P: (248) 733-3907
        <br />
        ASKPSYCHOLOGICAL@GMAIL.COM
      </div>
    </div>
  </div>
</div>

<style>
  .contact-container {
    display: flex;
    flex-direction: column;
    margin: 2em 4em;
    gap: 2em;
  }

  .img-container {
    flex: 1;
    max-width: 100%;
    overflow: hidden;
    min-width: 300px;
  }

  .img-container > img {
    position: relative;
    top: 15px;
    width: 100%;
    min-width: 300px;
    height: auto;
    opacity: 0.5;
  }

  .content-container {
    margin: auto;
    display: flex;
    justify-items: center;
    gap: 5em;
  }

  .info-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1em;
    margin: 0 auto;
    align-self: flex-start;
  }

  .info {
    color: var(--ask-purple);
    background-color: white;
    font-size: 24px;
    text-align: center;
    padding: 1em;
    border-radius: 8px;
    box-shadow: var(--ask-shadow);
    word-break: break-all;
  }

  @media (max-width: 769px) {
    .contact-container {
      margin: 2em 1em;
    }

    .content-container {
      flex-wrap: wrap;
    }
  }

  @media (max-width: 420px) {
    .info {
      padding: 0.5em;
      font-size: 20px;
    }

    .img-container > img,
    .img-container {
      min-width: 75px;
    }
  }

  @media (max-width: 350px) {
    .info {
      padding: 0.25em;
      font-size: 16px;
    }
    .content-container {
      gap: 0;
    }
  }
</style>

<script lang="ts">
  import PageTitle from "$lib/components/PageTitle.svelte";
  import ContactTypes from "$lib/components/icons/ContactTypes.svelte";
</script>

<div class="contact-container">
  <PageTitle title="CONTACT US" />

  <div class="content-container">
    <div class="img-container">
      <img
        src="https://askpsychologicalservices.com/images/d93bea1563a5721e4aa0bdbc0bb36799.png"
        alt="ASK Partners"
      />
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

  img {
    opacity: 0.2;
    transform: scale(0.8) translate(0, -200px);
  }

  .img-container {
    overflow: hidden;
    height: 700px;
  }

  .content-container {
    display: flex;
    width: 100%;
  }

  .info-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1em;
  }

  .info {
    color: rgb(62, 4, 69);
    background-color: white;
    font-size: 24px;
    text-align: center;
    padding: 1em;
    border-radius: 8px;
    box-shadow:
      0.7px 0.6px 1px rgba(22, 22, 22, 0.5),
      2.3px 2.1px 3.5px -0.8px rgba(22, 22, 22, 0.5),
      5.7px 5.2px 8.7px -1.7px rgba(22, 22, 22, 0.5),
      13.8px 12.7px 21.1px -2.5px rgba(22, 22, 22, 0.5);
  }
</style>

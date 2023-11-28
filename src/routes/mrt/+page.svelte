<script lang="ts">
  import PageTitle from "$lib/components/PageTitle.svelte";
  import FingerPoint from "$lib/components/icons/FingerPoint.svelte";
  import Brain from "$lib/components/icons/Brain.svelte";

  let outerWidth: number;
  const date = new Date()
  const month = date.getMonth() + 1
  const year = date.getFullYear()
  const calendlyMonth = year + "-" + month
</script>

<svelte:window bind:outerWidth />

<div class="mrt-container">
  <PageTitle title="MORAL RECONATION THERAPY (MRT)" />

  <div class="content-container">
    {#if outerWidth > 769}
      <div class="svg-container">
        <Brain />
        <FingerPoint />
      </div>
    {/if}
    <div class="info-container">
      <h4>$25 | session</h4>
      <div>
        <a href="https://www.moral-reconation-therapy.com/" target="_blank"
          >Moral Reconation Therapy</a
        > is a cognitive-behavioral treatment system that leads to enhanced moral
        reasoning, better decision making, and more appropriate behavior. This modality
        was developed in 1985 by Dr. Gregory Little and Dr. Kenneth Robinson, with
        over 200 published studies that have supported MRT-treated offenders to show
        significantly lower recidivism rates, as long as 20 years after treatment.
      </div>
      <h4>Active Groups:</h4>
      <div>General mrt group | Friday @ 2 pm via zoom</div>
      <div>
        MRT inappropriate sexual behaviors| Friday @ 11 AM & Saturday @ 9 am via
        zoom
      </div>
      <br />
      <div>
        <a
          href={`https://calendly.com/drgroth/meeting?month=${calendlyMonth}`}
          target="_blank"
        >
          *15- minute pre-screening/assessment | Dr. Karen Groth
        </a>
      </div>
    </div>
  </div>
  {#if outerWidth <= 769}
    <div class="svg-container">
      <Brain />
      <FingerPoint />
    </div>
  {/if}
</div>

<style>
  .mrt-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 4em;
    margin: 2em 4em;
  }

  .content-container {
    display: flex;
    gap: 4em;
  }

  .svg-container {
    display: flex;
    flex-direction: column;
  }

  .info-container {
    font-size: 24px;
  }

  @media (max-height: 769px) {
    .mrt-container {
      margin: 2em 1em;
    }

    .svg-container {
      margin: auto;
    }
  }
</style>

<script lang="ts">
  import PageTitle from "$lib/components/PageTitle.svelte";
  import mission from "$lib/images/mission.png"
  import puzzle from "$lib/images/puzzlepic.png"

  let missImg = "https://askpsychologicalservices.com/images/ce41d754ce7bec92107328b9415db40d.jpg"
  let puzzImg = "https://askpsychologicalservices.com/images/6121f58e06412d3a40e8430aba52e8cc.jpg"
</script>

<div class="mission-container">
  <PageTitle title={"OUR MISSION"} />

  <div class="body-img-container">
    <img
      class="body-img"
      src={mission}
      alt="Our mission"
    />
  </div>
  <div class="content">
    <p>
      At <b>ASK Psychological Services PLLC</b> our mission is to provide expert
      forensic psychological and mental health services to our community.
    </p>
    <p>
      We are committed to providing compassionate psychological services that
      improve the overall well-being of individuals and our society as a whole.
    </p>
    <p>
      Our practice is built on the core principles of <b>integrity, empathy,</b>
      and
      <b>respect</b> for all people.
    </p>
  </div>

  <div class="points-container">
    <div class="background-image" style:background-image={`url(${puzzle})`}></div>
    <div class="points">
      <h2>At ASK Psychological Services PLLC, we aim to:</h2>
      <ul>
        <li>
          Provide comprehensive assessments and evaluations that meet the
          highest standards of forensic psychology, delivering accurate and
          insightful findings to aid in legal proceedings.
        </li>
        <li>
          Offer evidence-based therapeutic interventions and counseling
          services, empowering individuals to navigate the challenges of their
          mental health and facilitating their journey toward healing and
          personal growth.
        </li>
        <li>
          Collaborate with legal professionals, courts, and other stakeholders
          to ensure that our forensic expertise contributes to fair and
          equitable outcomes in the justice system.
        </li>
        <li>
          Advocate for the de-stigmatization of mental health issues in our
          communities and within the criminal justice system.
        </li>
        <li>
          Continuously invest in our team's professional development, staying at
          the forefront of advancements in psychology, forensic practices, and
          treatment modalities.
        </li>
      </ul>
    </div>
  </div>
</div>

<style>
  .mission-container {
    display: grid;
    grid-template-rows: auto;
    grid-template-columns: 1fr 2fr;
    grid-template-areas: "title title" "img content" "points points";
    margin: 2em 8em;
    gap: 2em;
  }

  .body-img-container {
    grid-area: img;
  }

  .body-img {
    width: 100%;
    border-radius: 8px;
    box-shadow: var(--ask-shadow);

  }

  .content {
    grid-area: content;
  }

  p {
    font-size: 24px;
  }

  .points-container {
    grid-area: points;
    position: relative;
    padding: 1em 2em;
  }

  .background-image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-size: cover;
    background-repeat: no-repeat;
    opacity: 0.2;
  }

  li {
    font-size: 24px;
    margin: 1em 0;
  }

  @media (max-width: 769px) {
    .mission-container {
      grid-template-columns: 1fr;
      grid-template-areas: "title" "img" "content" "points";
      margin: 1em;
    }

    .points-container {
      padding: 0;
    }
  }
</style>

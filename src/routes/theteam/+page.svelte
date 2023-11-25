<script lang="ts">
  import PageTitle from "$lib/components/PageTitle.svelte";
  import PlayerCard from "$lib/components/PlayerCard.svelte";
  import PlayerInfo from "$lib/components/PlayerInfo.svelte";

  const players = [
    {
      img: "https://askpsychologicalservices.com/images/7ccd0fa348e7b1019cb6f835cb134d33.png",
      title: "PSYCHOLOGIST (LLP)",
      name: "Dr. Karen Groth",
      degree: "ED.D, LLP, CCFC, CCSOTS",
      translate: "0, -50px",
      scale: "1",
      infoTitle:
        "Doctor of Education in Counseling Psychology | Master of Science in Clinical & Counseling Psychology | Certified clinical forensic counselor | Certified clinical sex offender treatment specialist | Certified juvenile sex offender counselor | National MRT Trainer & Facilitator",
      specialties: `  <h4>Practice Specialties:</h4>
  <p>
    Psychological Assessments | Forensic ASSESSMENTS| Risk Assessments | Law
    Enforcement Candidate Assessments
  </p>
  <div><b>Individual & Couples Therapy (18+)</b></div>
  <div>
    depression | Anxiety | Sexual behavior problems | relationship issues |
    Legal Issues | Substance Use/Addictions | unhealthy food relationships
  </div>`,
      edu: null,
      id: "drGroth"
    },
    {
      img: "https://askpsychologicalservices.com/images/4e7820b65742e490933af70ef61b5a71.png",
      title: "PSYCHOLOGIST (LLP)",
      name: "Samantha Blair",
      degree: "MA, LLP",
      translate: "0, -50px",
      scale: "1.5",
      infoTitle:
        "Master in Psychology | Michigan School of Professional Psychology Bachelor in Neuroscience | Michigan State University",
      specialties: `  <h4>Individual psychotherapy for adolescents & adults (12+)</h4>
  <p>
    Anxiety & Depression | Mood Disorders | Anger Management | Legal Involvement
    Psychological Assessments | Psychological Evaluations | Risk Assessments |
    MRT
  </p>`,
      edu: "Certificate in Forensic Criminology | Univ. Massachusetts, Lowell MRT Facilitator",
      id: "samantha"
    },
    {
      img: "https://askpsychologicalservices.com/images/5b593f625977b47c24cb402fbfca202c.png",
      title: "SOCIAL WORKER (LMSW)",
      name: "Arianna Der Manulian",
      degree: "LMSW, CST, CFSW",
      translate: "0, 30px",
      scale: "1.75",
      infoTitle:
        "Master in Social Work | University of Michigan Bachelor of Arts in Psychology | Michigan State University",
      specialties: `  <h4>Individual psychotherapy for adults (18+)</h4>
  <p>
    Sex Therapy | Trauma/PTSD | Mood Disorders | Substance Use/Abuse Legal
    Involvement
  </p>`,
      edu: "Certified Sex Therapist (CST) | AASECT Certified Forensic Social Worker (CFSW) | NAFC Trained in EMDR, MRT, and IFS",
      id: "arianna"
    },
  ];

</script>

<div class="team-container" id="top">
  <PageTitle title="MEET THE TEAM" />
  <div class="team-player-container">
    {#each players as player}
      <PlayerCard
        img={player.img}
        title={player.title}
        name={player.name}
        degree={player.degree}
        translate={player.translate}
        scale={player.scale}
        id={player.id}
      />
    {/each}
  </div>
  {#each players as player}
    <PageTitle title={player.name} />
    <div class="player-info" id={player.id}>
      <PlayerCard
        img={player.img}
        title={player.title}
        name={player.name}
        degree={player.degree}
        translate={player.translate}
        scale={player.scale}
        hasLink
      />
      <PlayerInfo
        infoTitle={player.infoTitle}
        specialties={player.specialties}
        edu={player.edu}
      />
    </div>
  {/each}
</div>

<style>
  .team-container {
    display: flex;
    flex-direction: column;
    gap: 4em;
    margin: 2em 4em;
  }

  .team-player-container {
    display: flex;
    gap: 5em;
    justify-content: center;
    flex-wrap: wrap;
  }

  .player-info {
    display: flex;
    gap: 5em;
  }

  @media (max-width: 769px) {
    .player-info {
      gap: 1em;
      flex-wrap: wrap;
      justify-content: center;
    }
  }
</style>

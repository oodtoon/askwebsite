<script lang="ts">
  import PageTitle from "$lib/components/PageTitle.svelte";
  import ServicesLink from "$lib/components/ServicesLink.svelte";
  import ClickHere from "$lib/components/icons/ClickHere.svelte";
  import ComingSoon from "$lib/components/icons/ComingSoon.svelte";
  import GroupCard from "$lib/components/GroupCard.svelte";
  import AltLearnMore from "$lib/components/icons/AltLearnMore.svelte";
  import Dots from "$lib/components/icons/Dots.svelte";

  const linkInfoList = [
    {
      img: "https://askpsychologicalservices.com/images/3bb88b6d9eab8a6fcd867c13c954aaf2.jpg",
      type: "Individual Therapy",
      top: "30%",
      right: "",
      class: "indv-container",
      cost: "$145",
      costInfo: "session Cash Pay (*sliding scale offered)",
      paymentInfo: "**Some insurance Accepted**",
      addtnlInfo:
        "One-on-one psychotherapy uniquely tailored to your individual goals.",
      title: "Areas of Specialty:",
      content:
        "legal Involvement | Problematic sexual behavior | Addiction |  Relationship difficulties | Trauma/Attachment Injuries | Mood disorders | Anxiety/Adjustment Disorders | Depression | Sex Therapy | OCD | Coping Skills | Emotional Regulation | Life Transitions | School/Peer Issues | Self-Esteem | Stress | Women's Issues | Unhealthy food relationships",
      clickHere: false,
      comingSoon: false,
      anchorInfo: "",
      id: "individual-info",
    },
    {
      img: "https://askpsychologicalservices.com/images/a9a1ae111ba39e4862ad62421ae87336.jpg",
      type: "Assessments",
      top: "",
      right: "40%",
      class: "assessment-container",
      cost: "$1000+",
      costInfo: "Assessment",
      paymentInfo: "**Insurance does not cover forensic assessments**",
      addtnlInfo:
        "All assessments include A clinical interview, document review, psychosocial history, mental status exam, psychological testing, and a written report.",
      title: "Assessment types:",
      content: `<ul>
    <li>Psychological evaluation for diagnosis & treatment planning</li>
    <li>Criminogenic risk assessment</li>
    <li>Forensic psychological assessment</li>
    <li>Psychosexual risk assessment</li>
    <li>Juvenile lifer evaluations</li>
    <li>Macomb county mental health assessment for gun charges</li>
    <li>Federal cases</li>
    <li>DHHS/CPS Assessments</li>
    <li>Law enforcement candidate evaluations</li>
  </ul>`,
      clickHere: true,
      comingSoon: false,
      anchorInfo: "For More Information:",
      id: "assessments-info",
    },
    {
      img: "https://askpsychologicalservices.com/images/b1f68e2dab2cc0da80fb6219efb5afaa.jpg",
      type: "Group Therapy",
      top: "10%",
      right: "50%",
      class: "group-container",
      cost: "$25",
      costInfo: "group session",
      addtnlInfo:
        "Psychotherapy offered in a group format, usually between 3-12 people; facilitated by one or two therapists. All groups meet virtually",
      title: "Current Groups:",
      content: `  <h4>MRT: sexually inappropriate behavior(s)</h4>
  <ul>
    <li>Friday @ 11 AM & Saturday @ 9 AM</li>
  </ul>
  <h4>MRT: General</h4>
  <ul>
    <li>Friday @ 2 PM</li>
  </ul>
  <h4>Women’s breaking the chains of trauma</h4>
  <ul>
    <li>Monday @ 4 PM</li>
  </ul>`,
      clickHere: false,
      comingSoon: true,
      anchorInfo: "",
      id: "group-info",
    },
  ];

  const groupInfoList = [
    {
      title: "Men's Trauma Group",
      time: "Every other monday at 4 PM",
      start: "Beginning  January 2024",
      isLink: false,
    },
    {
      title: "Juvenile MRT Group",
      time: "Tuesdays 4pm",
      start: "Beginning  January 2024",
      isLink: false,
    },
    {
      title: "Fertility Support Group",
      time: "Coming 2024",
      start: null,
      isLink: false,
    },
    {
      title: "MRT Processing Group",
      time: "Date & time: TBD",
      start: null,
      isLink: false,
    },
    {
      title: "Resilient Women Support Group",
      time: "Date & time: TBD",
      start: null,
      isLink: false,
    },
    {
      title: "",
      time: "",
      start: null,
      isLink: true,
    },
  ];

  function handleAnchorClick (event: any) {
		event.preventDefault()
		const link = event.currentTarget as HTMLAnchorElement
		const anchorId = new URL(link.href).hash.replace('#', '')
		const anchor = document.getElementById(anchorId)
		window.scrollTo({
			top: anchor!.offsetTop,
			behavior: 'smooth'
		})
	}
</script>

<div class="services-container">
  <div class="top-container" id="top">
    <PageTitle title={"OUR SERVICES"} />
    <div class="links">
      {#each linkInfoList as link}
        <ServicesLink
          img={link.img}
          type={link.type}
          top={link.top}
          right={link.right}
          id={link.id}
          {handleAnchorClick}
        />
      {/each}
    </div>
  </div>

  {#each linkInfoList as link}
    <div class={`${link.class} info`} id={link.id}>
      <ServicesLink
        img={link.img}
        type={link.type}
        top={link.top}
        right={link.right}
        {handleAnchorClick}
        isLarge
        isToTop
      />
      <section>
        <div>{link.cost} | {link.costInfo}</div>
        {#if link.paymentInfo}
          <div>{link.paymentInfo}</div>
        {/if}
        <br />
        <div>{link.addtnlInfo}</div>
        <h3>{link.title}</h3>
        <div>{@html link.content}</div>
        {#if link.comingSoon}
          <div class="click-here">
            <a href="#group" on:click={handleAnchorClick}><ComingSoon /></a>
          </div>
        {/if}

        {#if link.clickHere}
          <div class="click-here">
            <div>{link.anchorInfo}</div>
            <a href="#assessment" on:click={handleAnchorClick}><ClickHere /></a>
          </div>
        {/if}
      </section>
    </div>
  {/each}
  <section class="assessment-info addtnl" id="assessment">
    <PageTitle title="WHAT IS A PSYCHOLOGICAL ASSESSMENT?" />
    <div>
      A <b>PSYCHOLOGICAL ASSESSMENT</b> IS DESIGNED TO HELP GAIN A BETTER UNDERSTANDING
      OF A PERSON'S OVERALL PSYCHOLOGICAL FUNCTIONING. THIS MAY INCLUDE THE DIAGNOSIS
      OF MENTAL HEALTH ISSUES, IDENTIFICATION OF CONCERNS, AND TREATMENT RECOMMENDATIONS.
      WE ALSO CONDUCT PSYCHOLOGICAL ASSESSMENTS FOR POLICE CANDIDATES TO DETERMINE
      IF THEY ARE APPROPRIATE FOR WORK IN LAW ENFORCEMENT,
    </div>
    <div>
      <b>FORENSIC PSYCHOLOGICAL ASSESSMENTS</b> ARE USED FOR INDIVIDUALS WITH CURRENT
      OR PENDING LEGAL/CRIMINAL JUSTICE INVOLVEMENT. THESE TYPES OF ASSESSMENTS TYPICALLY
      INCLUDE THE SAME COMPONENTS AS A PSYCHOLOGICAL EVALUATION BUT WITH ADDITIONAL
      EMPHASIS ON CRIMINOGENIC BEHAVIORS AND RISK FACTORS. FORENSIC ASSESSMENTS ARE
      A VALUABLE TOOL TO ASSIST ATTORNEYS, JUDGES, PROBATION, PAROLE, AND OTHER LEGAL
      AND CRIMINAL JUSTICE PROVIDERS IN DECISION-MAKING.
    </div>
  </section>
  <section class="group-info addntl" id="group">
    <PageTitle title="UPCOMING VIRTUAL GROUPS" />
    <div class="group-dates">
      {#each groupInfoList as group}
        {#if !group.isLink}
          <GroupCard
            title={group.title}
            time={group.time}
            start={group.start}
          />
        {:else}
          <a href="#program" on:click={handleAnchorClick}>
            <AltLearnMore />
          </a>
        {/if}
      {/each}
    </div>
  </section>
  <section class="program-info addtnl" id="program">
    <PageTitle title="BREAKING THE CHAINS OF TRAUMA GROUPS  MEN & WOMEN" />
    <h2>
      An 8-step program designed to alleviate trauma symptoms in a group format
    </h2>
    <em>Women’s First Group: Monday, Nov. 6 at 4 PM via Zoom</em>
    <em>Men’s Group Every other Monday at 4 PM Starting January 2024</em>
    <Dots />
    <h2>Now accepting referrals</h2>
    <Dots />
    <h3>
      PLEASE <a href="/contact">CONTACT US</a> FOR MORE INFORMATION & TO REGISTER
    </h3>
  </section>
</div>

<style>
  .services-container {
    display: grid;
    grid-template-rows: auto;
    grid-template-columns: 1fr;
    grid-template-areas: "title" "links" "indv" "assessment" "group" "assessment-info" "group-info" "program-info";
    margin: 2em 8em;
    gap: 5em;
    scroll-behavior: smooth;
  }

  .top-container {
    display: flex;
    flex-direction: column;
    gap: 2em;
    grid-area: title;
  }

  .links {
    grid-area: links;
    display: flex;
    justify-content: center;
    gap: 2em;
    flex-wrap: wrap;
  }

  .indv-container {
    grid-area: indv;
  }

  .assessment-container {
    grid-area: assessment;
  }

  .group-container {
    grid-area: group;
  }

  .info {
    display: flex;
    gap: 4em;
    font-size: 24px;
  }

  .click-here {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .addtnl {
    font-size: 24px;
    font-weight: 200;
    display: flex;
    flex-direction: column;
    gap: 2em;
  }

  .assessment-info {
    grid-area: assessment-info;
  }

  .group-info {
    grid-area: group-info;
  }

  .group-dates {
    display: flex;
    flex-direction: row;
    gap: 2em;
    flex-wrap: wrap;
    justify-content: center;
    font-size: 24px;
    font-weight: 200;
  }

  .program-info {
    grid-area: program-info;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>

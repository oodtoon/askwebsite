<script lang="ts">
  import Menu from "./icons/Menu.svelte";
  import Exit from "./icons/Exit.svelte";
  import Dropdown from "$lib/components/Dropdown.svelte";

  let outerWidth: number;
  let isDropdownVisible: boolean = false;

  const navItems = [
    {
      title: "Home",
      link: "/",
    },
    {
      title: "Our Mission",
      link: "/mission",
    },
    {
      title: "Services",
      link: "/services",
    },
    {
      title: "Hours & Location",
      link: "/hours&location",
    },
    {
      title: "Meet the Team",
      link: "/theteam",
    },
    {
      title: "Moral Reconation Therapy",
      link: "/mrt",
    },
    {
      title: "Contact Us",
      link: "/contact",
    },
  ];

  function handleDropdown() {
    isDropdownVisible = !isDropdownVisible;
  }

  function handleAnchorClick() {
    isDropdownVisible = false;
  }

  function handleDocumentClick(event: MouseEvent) {
    if (isDropdownVisible) {
      const target = event.target as HTMLElement;
      const dropdown = document.querySelector(".dropdown");
      if (
        !dropdown?.contains(target) &&
        !target.classList.contains("menu-btn") &&
        !target.classList.contains("drop-link")
      )
        isDropdownVisible = false;
    }
  }

  $: if (outerWidth > 769) {
    isDropdownVisible = false;
  }
</script>

<svelte:document on:click={handleDocumentClick} />
<svelte:window bind:outerWidth />

<nav>
  {#if outerWidth > 769}
    {#each navItems as item}
      <span><a class="nav-link" href={item.link}>{item.title}</a></span>
    {/each}
  {:else}
    <button on:click={handleDropdown} class="menu-btn">
      {#if !isDropdownVisible}
        <Menu />
      {:else}
        <Exit />
      {/if}
    </button>
  {/if}
  {#if isDropdownVisible}
    <Dropdown>
      {#each navItems as item}
        <div class="dropdown">
          <a
            class="nav-link drop-link"
            href={item.link}
            on:click={handleAnchorClick}>{item.title}</a
          >
        </div>
      {/each}
    </Dropdown>
  {/if}
  <span class="img-container">
    <a href={"/"}
      ><img
        src={"https://askpsychologicalservices.com/images/3cc98553e78333ece2ac284d66c46fbb.png"}
        alt="ask logo"
        class="ask-logo"
      /></a
    >
  </span>
</nav>

<style>
  nav {
    background-color: var(--ask-purple);
    display: flex;
    align-items: center;
    width: 100%;
    position: relative;
  }

  button {
    background-color: transparent;
    border: transparent;
    margin-left: 2em;
  }

  .nav-link {
    color: white;
    text-decoration: none;
    font-size: 20px;
  }

  .dropdown {
    margin: 1em;
  }

  span {
    margin: 1em;
  }

  .img-container {
    margin-left: auto;
    margin-right: 4em;
  }

  .ask-logo {
    border-radius: 50% 50% 0 0;
    height: 5em;
  }

  @media (max-width: 320px) {
    .img-container {
      margin-right: 1em;
    }
  }
</style>

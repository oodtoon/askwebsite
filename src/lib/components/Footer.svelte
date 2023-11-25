<script lang="ts">
  let date = new Date();
  let year = date.getFullYear();

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
</script>

<footer>
  <div class="footer-info">
    {#each navItems as item}
      <a class="nav-link" href={item.link}>{item.title}</a>
    {/each}
    <div class="rights-info">
      <div>ASK Psychological Services</div>
      <div>© {year} All Rights Reserved</div>
    </div>
  </div>
</footer>

<style>
  footer {
    background-color: rgb(62, 4, 69);
    display: flex;
    align-items: center;
    padding: 1em;
  }

  a {
    color: white;
    text-decoration: none;
  }

  .rights-info {
    color: white;
    margin-top: auto;
  }

  .footer-info {
    margin: auto;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    max-height: 200px;
    gap: 0 1em;
  }

  .nav-link {
    margin: .2em 0;
  }

  @media (max-width: 400px) {
    .footer-info {
      max-height: 400px;
    }
  }
</style>

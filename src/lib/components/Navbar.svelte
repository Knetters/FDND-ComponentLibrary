<script>
  import { onMount } from "svelte";

  onMount(() => {
    // nav toggle - select button and links
    const navToggle = document.querySelector("#navToggle");
    const nav = document.querySelector("#nav-links");

    // add event listener
    navToggle.addEventListener("click", () => {
      nav.classList.toggle("nav-open");
    });
  });
</script>

<div class="navbar">
  <div class="container flex-nav">
    <div class="nav-header">
      <img class="logo" src="/assets/logo_spatwater.png" alt="logo spatwater" />
      <button class="nav-toggle" id="navToggle">
        <i class="ri-menu-line" />
      </button>
    </div>
    <nav class="nav-links" id="nav-links">
      <ul>
        <li class="nav-link"><a href="/">Home</a></li>
        <li class="nav-link"><a href="/over">Over</a></li>
        <li class="nav-link"><a href="/expertise">Expertise</a></li>
        <li class="nav-link"><a href="/#projecten">Projecten</a></li>
        <li class="nav-link"><a href="/#kennisbank">Kennisbank</a></li>
        <li class="nav-link"><a href="/team">Team</a></li>
        <li class="nav-link"><a href="/contact"><span>Contact</span></a></li>
      </ul>
    </nav>
  </div>
</div>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Poppins&display=swap");
  @import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css");

  :root {
    --spat: #7faec5;
    --lg-bg: #fafafa;
    --green: #4ecd5d;
    --darkblue: #384b61;
  }

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  .container {
    max-width: 100vw;
    margin: 0 auto;
    padding: 0.8rem 2rem;
  }

  a {
    color: var(--spat);
    text-decoration: none;
  }

  .nav-link {
    list-style: none;
    margin: 20px 0;
    border-bottom: 2px solid black;
    margin-left: 2rem;
  }

  /* Navbar */
  .navbar {
    background: white;
    box-shadow: -1px 0 4px rgba(14, 55, 63, 0.15);
    height: 4.5rem;
    position: fixed;
    width: 100%;
    z-index: 9999;
  }

  .flex-nav {
    display: flex;
    flex-direction: column;
  }

  .nav-header img {
    width: 6.5rem;
  }

  .nav-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .nav-toggle {
    margin-top: 0.5rem;
    border: transparent;
    background: transparent;
    color: var(--darkblue);
    font-size: 1.5rem;
  }

  .nav-links {
    height: 0;
    overflow: hidden;
  }

  /* .nav-open {
    height: 100vh;
  } */

  @media only screen and (min-width: 900px) {
    .nav-toggle {
      display: none;
    }

    .nav-header {
      display: block;
    }

    .flex-nav {
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
      padding: 0.3rem 2.5rem;
    }

    .nav-links {
      height: auto;
    }

    ul {
      text-align: center;
    }

    .nav-link {
      display: inline-block;
      border-bottom: none;
    }

    .nav-links span {
      background: var(--green);
      color: white;
      padding: 0.5rem 15px;
      border-radius: 4px;
    }
  }
</style>

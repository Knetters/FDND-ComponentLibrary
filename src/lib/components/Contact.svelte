<script>
  import { onMount } from "svelte";

  onMount(() => {
    console.log(data);
  });

  export let data;
  import { FormContact } from "$lib/index.js";
</script>

<section class="contact">
  <h2>Contact</h2>
  <p>Voel je vrij om contact met ons op te nemen</p>
  <section class="contact-section" id="experience">
    <div class="main-container">
      <FormContact />
    </div>
    <img src="assets/tree.png" alt="afbeelding boom naast invulformulier" />
  </section>
</section>

<style>
  section.contact {
    padding: 2em;
  }

  img {
    width: 90%;
  }

  h2 {
    padding-top: 2rem;
    color: var(--spat);
  }

  p {
    margin-bottom: 1rem;
    color: var(--darkblue);
    font-size: 0.8rem;
  }

  /* FORMULIER */

  .contact-section {
    container: sidebar / inline-size;
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  .contact {
    padding: 4rem 5rem;
    height: auto;
    background-color: var(--lg-bg);
  }

  /* CONTAINER QUERIES */
  @container sidebar (min-width: 700px) {
    img {
      margin-left: 2em;
      margin-top: -2em;
    }
  }

  @container sidebar (max-width: 700px) {
    img {
      display: none;
    }
    .main-container {
      width: 100vw;
      padding-right: 6em;
      grid-template-columns: 1fr;
    }
  }
</style>

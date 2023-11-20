<script>
</script>

<section
  class="expertise section">
  <h2 class="expertise-title">Expertise</h2>

  <div class="expertise__wrapper">
    <div class="expertise__card">
      <img class="expertise3" src="assets/Untitled4.png" alt="Illustratie klimaatadaptatie"/>
      <h3>Klimaatadaptatie</h3>
      <a href="#klimaat" class="button">
        <p class="button_text2">Meer informatie</p>
      </a>
    </div>

    <div class="expertise__card">
      <img class="expertise2" src="assets/Untitled3.png" alt="Illustratie waterkwaliteit"/>
      <h3>Waterkwaliteit</h3>
      <a href="#waterkwaliteit" class="button">
        <p class="button_text2">Meer informatie</p>
      </a>
    </div>
    
    <div class="expertise__card">
      <img class="expertise2" src="assets/brainlogo.png" alt="Illustratie B-Rain"/>
      <h3> B-Rain</h3>
      <a href="#brain" class="button">
        <p class="button_text2">Meer informatie</p>
      </a>
    </div>
  </div>
</section>

<style>
  .expertise {
    background-color: white;
    display: flex;
    flex-direction: column;
    position: relative;
  }

  .expertise-title {
    font-size: 1.5rem;
    color: var(--spat);
    font-weight: 600;
    text-align: left;
    margin-left: 2.5rem;
  }

  .expertise h3 {
    font-size: 1.3rem;
    color: var(
      --darkblue
    );
    font-weight: 600;
    text-align: center;
    padding-bottom: 1em;
  }

  .expertise__wrapper {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    padding: 4rem 2rem; 
    gap: 3rem;

    /* display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 6rem 6rem; 
    gap: 1rem; */

    /* display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr;
    padding: 4rem; */
  }

  .expertise__card {
    margin: 0 auto;
    height: 25em;
    width: 18em;
    border-radius: 4px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    box-shadow: 0
      4px 6px
      rgba(
        174,
        190,
        205,
        0.3
      );
    background-color: var(
      --lg-bg
    );
    color: var(
      --darkblue
    );
    transition: 0.3s
      ease-in;
  }

  .expertise__card
    img {
    width: 250px;
    padding-bottom: 2em;
  }
  .expertise__card
    .expertise2 {
    width: 250px;
    padding-top: 1em;
    padding-bottom: 0.5em;
  }
  .expertise__card:nth-child(
      2
    ) {
    background-color: var(
      --lg-bg
    );
  }
  .expertise__card:nth-child(
      3
    ) {
    background-color: var(
      --lg-bg
    );
  }

  .expertise__card:hover {
    transform: scale(
      1.075
    );
    transition: 0.3s
      ease-in;
    cursor: pointer;
  }

  .button {
    display: inline-block;
    background-color: var(
      --green
    );
    color: white;
    padding: 0.7rem
      1rem;
    height: 50px;
    border-radius: 5px;
    font-weight: var(
      --font-semi-bold
    );
    transition: 0.3s;
    text-decoration: none;
  }

  .button_text2 {
    text-decoration: none;
    color: white;
    font-size: 1rem;
  }

  @media screen and (min-width: 1024px) {
    .expertise__wrapper {
    flex-direction: row;
    justify-content: space-around;
    padding: 4rem 8rem; 
    gap: 3rem;
  }

  .expertise-title{
    margin-left: 14rem;
  }
  }

</style>

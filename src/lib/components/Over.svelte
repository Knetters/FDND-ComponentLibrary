<script>
</script>

<!--==================== ABOUT ====================-->
<section class="climate-container">
  <div class="inner-section">
    <div class="horizontal-flex-row">
      <div class="text-container">
        <h2>Over SPATwater</h2>
        <p>SPATwater bestaat uit een nieuwe generatie enthousiaste hydrologen die met een technische achtergrond nét wat anders kijken naar ruimtelijke opgaven. De uitdagingen zijn enorm, maar de kansen die het biedt nog groter.</p>
        <p>Met expertise op het gebied van waterkwaliteit, de Kaderrichtlijn Water en klimaatadaptatie helpt SPATwater overheden en bedrijven om toekomstbestendig en waterrobuust te worden.</p>
        <p>Wij voeren geen analyse uit zonder handelingsperspectief en bieden zowel creatieve als praktische oplossingen.</p>

        <a href="#expertise" class="button">Onze expertise</a>
      </div>
      <div class="image-container">
        <img src="assets/tree.png" alt="boom illustratie" />
      </div>
    </div>
  </div>
</section>

<style>
  section {
    width: 100%;
    padding-top: 5rem;
    padding-bottom: 5rem;
    margin-bottom: 5rem;
    background: var(--lg-bg);
  }

  .inner-section {
    width: 70%;
    margin-left: 15%;
    margin-bottom: 3rem;
  }

  h2 {
    padding: 0rem;
    color: var(--spat);
    margin-bottom: 1rem;
  }

  .horizontal-flex-row {
    width: 100%;
    display: flex;
    gap: 10%;
  }

  .text-container {
    width: 50%;
  }

  img {
    height: 20rem;
    object-fit: cover;
    border-radius: .5rem;
  }

  /* Mobiele weergaven */
  @media only screen and (max-width: 1100px) {
    .horizontal-flex-row {
      flex-direction: column;
    }

    .text-container {
      width: 100%;
    }

    .image-container {
      width: 100%;
      margin-top: 1rem;
    }

    img {
      height: 10rem;
      width: 100%;
      z-index: -1;
      object-fit: contain;
    }

    .inner-section {
      /* padding: 0rem 2.5rem; */
      width: 70%;
      margin-bottom: 2rem;
    }
  }
</style>

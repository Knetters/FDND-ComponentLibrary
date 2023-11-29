<script>
  export let data
  console.log(data)
</script>

{#each data.klimaatadaptaties as klimaat}
  <div
    class="light-background"
  >
    <section
      class="first-section"
    >
      <div
        class="inner-section"
      >
        <div
          class="horizontal-flex-row"
        >
          <div
            class="text-container"
          >
            <h2>
              {klimaat.title}
            </h2>
            <p
              class="bold-text"
            >
              {klimaat
                .boldText
                .text}
            </p>
            <p>
              {klimaat
                .content
                .text}
            </p>
            <ul
              aria-labelledby="klimaatTitel"
            >
              <li>
                <i
                  class="fa fa-arrow-right"
                  aria-hidden="true"

                ></i>
                {klimaat
                  .lijst
                  .text}
              </li>
            </ul>
          </div>
          <div
            class="image-container"
          >
            <img
              src={klimaat
                .image
                .url}
              alt="Afbeelding ter illustratie van Klimaatadaptatie"
              loading="lazy"
            />
          </div>
        </div>
      </div>
    </section>
  </div>
{/each}

{#each data.gemeentens as gemeenten}
  <section>
    <div
      class="inner-section"
    >
      <div
        class="horizontal-flex-row"
      >
        <div
          class="image-container"
        >
          <img
            class="mobile-image"
            src={gemeenten
              .image
              .url}
            alt="Afbeelding ter illustratie van Klimaatadaptatie"
            loading="lazy"
          />
        </div>
        <div
          class="text-container"
        >
          <h2>
            {gemeenten.title}
          </h2>
          <p
            class="bold-text"
          >
            {gemeenten
              .boldTekst
              .text}
          </p>
          <p>
            {gemeenten
              .content
              .text}
          </p>
        </div>
      </div>
    </div>
  </section>
{/each}

{#each data.bedrijventerreinens as bedrijf}
  <section>
    <div
      class="inner-section"
    >
      <div
        class="horizontal-flex-row"
      >
        <div
          class="text-container"
        >
          <h2>
            {bedrijf.title}
          </h2>
          <p
            class="bold-text"
          >
            {bedrijf
              .boldTekst
              .text}
          </p>
          <p>
            {bedrijf
              .content
              .text}
          </p>
          <ul
            aria-labelledby="klimaatTitel"
          >
            <li>
              <i
                class="fa fa-arrow-right"
                aria-hidden="true"
              ></i>
              {bedrijf
                .lijst
                .text}
            </li>
          </ul>
        </div>
        <div
          class="image-container"
        >
          <img
            src={bedrijf
              .image
              .url}
            alt="Afbeelding ter illustratie van Klimaatadaptatie"
            loading="lazy"
          />
        </div>
      </div>
    </div>
  </section>
{/each}

<style>
  section {
    width: 100%;
    background: var(
      --lg-bg
    );
    padding: 1rem
      0rem 2rem 0rem;
  }

  .first-section {
    margin-top: 5rem;
  }

  .light-background {
    background: var(
      --lg-bg
    );
    padding: 1rem
      0rem 2rem 0rem;
  }

  .inner-section {
    width: 70%;
    margin: 0 auto
      3rem auto;
  }

  h2 {
    padding: 0rem;
    color: var(
      --spat
    );
    margin-bottom: 1rem;
    /* margin-top: 3rem; */
  }

  .bold-text {
    font-weight: 600;
  }

  ul {
    list-style: none;
    font-size: 0.8rem;
    color: var(
      --darkblue
    );
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
    border-radius: 0.5rem;
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
      object-fit: cover;
    }
    .mobile-image {
      display: block;
    }
    .inner-section {
      /* padding: 0rem 2.5rem; */
      width: 70%;
      margin-bottom: 2rem;
    }
  }
</style>

<script>
</script>

<!-- Klimaat section -->

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
            Klimaatadaptatie
          </h2>
          <p
            class="bold-text"
          >
            Als meer
            dan 60%
            van een
            gemeente
            private
            grond
            is… dan
            is het
            noodzakelijk
            om deze
            grond
            klimaatadaptief
            te
            maken.
          </p>
          <p>
            Ons
            vertrekpunt
            is dat
            een
            groot
            deel van
            een
            gemeente
            bestaat
            uit
            private
            grond
            (tuinen,
            daken,
            bedrijventerreinen)
            en dat
            het
            absoluut
            noodzakelijk
            is dat
            deze
            private
            ruimte
            klimaatadaptief
            ingericht
            moet
            worden.
            Elk
            perceel
            vraagt
            om
            maatwerk,
            maar het
            is
            onmogelijk
            om elke
            tuin in
            te gaan.
          </p>
          <ul>
            <li>
              <i
                class="fa fa-arrow-right"
                aria-hidden="true"
              /> Hoe
              los je
              dit probleem
              op?
            </li>
            <li>
              <i
                class="fa fa-arrow-right"
                aria-hidden="true"
              /> Hoe
              zet je
              subsidiestromen
              efficiënt
              in?
            </li>
            <li>
              <i
                class="fa fa-arrow-right"
                aria-hidden="true"
              /> Hoe
              activeer
              je bewoners?
            </li>
          </ul>
        </div>
        <div
          class="image-container"
        >
          <img
            src="assets/projects1.png"
            alt=""
          />
        </div>
      </div>
    </div>
  </section>

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
            src="assets/projects4.png"
            alt=""
          />
        </div>
        <div
          class="text-container"
        >
          <h2>
            Gemeenten
          </h2>
          <p
            class="bold-text"
          >
            Wij
            kunnen
            elke
            bewoner
            in uw
            gemeente
            een
            persoonlijk
            klimaatadaptief
            advies
            geven
            zonder
            elke
            tuin in
            te gaan.
          </p>
          <p>
            Wij
            gebruiken
            ruimtelijke
            data en
            sociale
            kennis
            uit de
            buurt om
            de
            gemeente
            gedetailleerd
            in kaart
            te
            brengen.
            In
            combinatie
            met
            veldwerk
            kunnen
            wij op
            postcode,
            buurt of
            wijkniveau
            klimaatadaptieve
            maatregelen
            personaliseren
            en
            prioriteren
            in de
            private
            ruimte.
            Hiermee
            maken
            wij de
            private
            ruimte
            waterrobuust,
            waterveilig,
            hitte-
            en
            droogtebestendig.
          </p>
        </div>
      </div>
    </div>
  </section>

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
            Bedrijventerreinen
          </h2>
          <p
            class="bold-text"
          >
            Bedrijventerreinen
            zijn
            vaak
            versteend,
            privaat
            terrein
            met veel
            oppervlakte.
          </p>
          <p>
            SPATwater
            richt
            zich op
            het
            activeren
            van
            werknemers
            en
            bedrijven
            door
            vraag en
            aanbod
            op het
            gebied
            van
            water
            bij
            elkaar
            te
            brengen
            door
            middel
            van
            ruimtelijke
            data en
            geeft
            handvatten
            om
            bedrijventerreinen
            te
            vergroenen.
          </p>
          <ul>
            <li>
              <i
                class="fa fa-arrow-right"
                aria-hidden="true"
              /> Het
              uitvoeren
              van stakeholders/netwerk
              analyses
            </li>
            <li>
              <i
                class="fa fa-arrow-right"
                aria-hidden="true"
              /> Co-creatie
              sessie
              organiseren
            </li>
            <li>
              <i
                class="fa fa-arrow-right"
                aria-hidden="true"
              /> Het
              uitvoeren
              van restwaterscans
            </li>
            <li>
              <i
                class="fa fa-arrow-right"
                aria-hidden="true"
              /> Het
              uitvoeren
              van klimaatanalyses
              en het
              koppelen
              van relevante
              maatregelen
            </li>
          </ul>
        </div>
        <div
          class="image-container"
        >
          <img
            src="assets/verg.png"
            alt=""
          />
        </div>
      </div>
    </div>
  </section>
</div>

<style>
  section {
    width: 100%;
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
    /* padding: 0rem 2.5rem; */
    width: 70%;
    margin-left: 15%;
    margin-bottom: 3rem;
  }

  h2 {
    padding: 0rem;
    color: var(
      --spat
    );
    margin-bottom: 1rem;
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
      display: none;
    }

    .inner-section {
      /* padding: 0rem 2.5rem; */
      width: 70%;
      margin-bottom: 2rem;
    }
  }
</style>

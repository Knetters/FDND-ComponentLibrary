<script>
  export let data
  console.log(data)
</script>

<section
  class="sponsor section"
>
  <div
    class="sponsor__container container grid"
  >
    {#each data.partner as partner}
      <a href={partner.link}>
        <img src={partner.image.url} alt="logo's partners" class="sponsor-img"/></a>
    {/each}
  </div>
</section>

<style>
  .sponsor {
    position: relative;
    padding: 6rem
      3.5rem;
  }

  .sponsor__container {
    display: grid;
    grid-template-columns: repeat(
      auto-fit,
      minmax(
        110px,
        1fr
      )
    );
    justify-items: center;
    row-gap: 3.5rem;
    align-items: center;
  }

  .sponsor__img {
    filter: invert(
      0.5
    );
  }

  .sponsor-img {
    width: 90px;
    height: auto;
    opacity: 0.5;
    filter: invert(
      0.7
    );
    transition: 0.3s;
  }

  /* Responsive */
  @media screen and (min-width: 720px) {
    .sponsor__container {
      grid-template-columns: repeat(
        3,
        1fr
      );
      justify-items: center;
      row-gap: 3.5rem;
    }

    .sponsor-img {
      width: 80px;
      opacity: 0.5;
      filter: invert(
        0.7
      );
      transition: 0.3s;
    }
  }
  @media screen and (min-width: 768px) {
    .sponsor-img {
      width: 90px;
    }
  }
</style>

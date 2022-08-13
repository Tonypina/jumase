<template>
  <section class="section p-0 has-background-grey">
    <div class="columns m-0">
      <div class="column p-0">
        <div class="hero is-fullheight contact-data is-flex is-justify-content-center is-align-items-center">
          <div class="has-text-white has-text-centered">
            <p class="is-size-3 has-text-weight-medium"><span class="has-text-orange">JUMASE</span> Informática</p>
            <p class="is-size-6"><span class="has-text-weight-medium">Oficina:</span>  55 8881 6485</p>
            <p class="is-size-6"><span class="has-text-weight-medium">Móvil:</span>  55 2563 6646</p>
            <p class="is-size-6"><span class="has-text-weight-medium">E-mail:</span> contacto@jumase.com.mx</p>
            <p class="is-size-6"><span class="has-text-weight-medium">Lunes a Viernes:</span> 9:00 - 18:00 hrs</p>
          </div>
        </div>
      </div>
      <div class="column p-0"></div>
    </div>
  </section>
</template>

<script>
  export default {
    name: 'ContactoView',
  }

</script>

<style lang="scss">
  .main-content {
    .container {
      margin: 0;
      max-width: 100vw !important;
      width: 100vw;

      .contact-data {
        background-color: #441709;
        background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100%25' height='100%25' viewBox='0 0 1600 800'%3E%3Cg %3E%3Cpolygon fill='%23692807' points='1600 160 0 460 0 350 1600 50'/%3E%3Cpolygon fill='%238f3905' points='1600 260 0 560 0 450 1600 150'/%3E%3Cpolygon fill='%23b44a04' points='1600 360 0 660 0 550 1600 250'/%3E%3Cpolygon fill='%23da5b02' points='1600 460 0 760 0 650 1600 350'/%3E%3Cpolygon fill='%23FF6C00' points='1600 800 0 800 0 750 1600 450'/%3E%3C/g%3E%3C/svg%3E");
        background-attachment: fixed;
        background-size: cover;
        position: relative;

        & div:first-child {
          z-index: 2;

          & p {
            padding-top: 1rem;
            
            &:first-child {
              letter-spacing: 1.3px;
            }
          }
        }

        &::after {
          background: rgba(0, 0, 0, 0.349);
          height: 100%;
          width: 100%;
          position: absolute;
          content: ' ';
        }
      }
    }
  }
</style>

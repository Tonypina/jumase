<template>
  <div>
    <nav class="navbar header has-shadow is-dark px-6" role="navigation" aria-label="main navigation">
      <div class="navbar-brand">
        <a class="navbar-item" href="/">
          <img src="~img/icon.png" alt="Jumase" />
        </a>

        <div class="navbar-burger">
          <span />
          <span />
          <span />
        </div>
      </div>

      <div class="navbar-menu">
        <div class="navbar-start ml-6 pl-6">

          <div v-for="(link, key) of navbar_links" :key="key" class="navbar-link pl-3 py-0">

            <!-- <div class="navbar-link pl-3"> -->

              <div v-if="link.title === 'Servicios' || link.title === 'Productos'" class="navbar-item is-hoverable has-dropdown is-mega">
                <!-- <div class="navbar-item is-hoverable has-dropdown is-mega"> -->

                  <NuxtLink :to="link.to" exact-active-class="is-active" class="pr-3">
                    {{ link.title }}
                  </NuxtLink>

                  <div class="navbar-dropdown">
                    <div class="container is-fluid">
                      <div class="columns">
                        <div class="column">

                          <h1 class="title is-6 is-mega-menu-title"> Sub menu</h1>
                          <a class="navbar-item" href="/2017/08/03/list-of-tags/">
                            <div class="navbar-content">
                              <p>
                                <small class="has-text-info">03 Aug 2017</small>
                              </p>
                              <p>New feature: list of tags</p>
                            </div>
                          </a>

                        </div>
                      </div>
                    </div>
                  </div>

                <!-- </div> -->
              </div>

              <div v-else class="navbar-item">
                <!-- <div class="navbar-item"> -->
                  <NuxtLink :to="link.to" exact-active-class="is-active">
                    {{ link.title }}
                  </NuxtLink>
                <!-- </div> -->
              </div>

            <!-- </div> -->

          </div>

        </div>

        <div class="navbar-end">
          <div class="navbar-item is-block has-text-centered">
            <p class="has-text-weight-semibold">JUMASE Informática</p>
            <p class="">La tecnología al servicio de tu negocio</p>
          </div>
        </div>
      </div>

    </nav>

    <section class="main-content">
      <div class="container">
        <Nuxt />
      </div>
    </section>
  </div>
</template>

<script>
  export default {
    name: 'DefaultLayout',
    data() {
      return {
        navbar_links: [{
            title: 'Inicio',
            to: {
              name: 'inicio'
            },
          },
          {
            title: 'Nosotros',
            to: {
              name: 'nosotros'
            },
          },
          {
            title: 'Servicios',
            to: {
              name: 'servicios'
            },
          },
          {
            title: 'Productos',
            to: {
              name: 'productos'
            },
          },
          {
            title: 'Contacto',
            // icon: null,
            to: {
              name: 'contacto'
            },
          },
        ],
      }
    },
  }

</script>

<style lang="scss" scoped>

</style>

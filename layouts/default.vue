<template>
  <div>
    <nav class="navbar header cs-shadow is-dark px-6" role="navigation" aria-label="main navigation">
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

              <div v-if="link.title === 'Servicios'" class="navbar-item is-hoverable has-dropdown is-mega">

                  <NuxtLink :to="link.to" exact-active-class="is-active" class="pr-3">
                    {{ link.title }}
                  </NuxtLink>

                  <div class="navbar-dropdown has-background-dark">
                    <div class="container is-fluid">

                        <div class="columns">
                            <div v-for="(group, group_key) of services" :key="group_key" class="column">
                              <div v-if="group_key === 0">
                                <h1 class="title is-6 is-mega-menu-title has-text-white"> 
                                  TIC's
                                </h1>
                              </div>
                              <div v-else-if="group_key === 1">
                                <h1 class="title is-6 is-mega-menu-title has-text-white"> 
                                  Seguridad                                  
                                </h1>
                              </div>
                              <div v-else-if="group_key === 2">
                                <h1 class="title is-6 is-mega-menu-title has-text-white"> 
                                  Software
                                </h1>
                              </div>
                              <div v-else>
                                <h1 class="title is-6 is-mega-menu-title has-text-white"> 
                                  Otros
                                </h1>
                              </div>
                              <div v-for="(service_group, service_group_key) of group" :key="service_group_key">
                                <NuxtLink v-for="(service, service_key) of service_group" :key="service_key" :to="service.to" class="navbar-item">
                                  <div class="navbar-content">
                                    <p>{{ service.title }}</p>
                                  </div>
                                </NuxtLink>  
                              </div>
                            </div>
                        </div>
                      
                    </div>
                  </div>
              </div>

              <div v-else class="navbar-item">
                  <NuxtLink :to="link.to" exact-active-class="is-active">
                    {{ link.title }}
                  </NuxtLink>
              </div>
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

    <footer class="footer has-background-dark p-0">
      <div class="container px-2 pt-6 pb-5">
        <div class="columns is-multiline">
          <div class="column is-half">
            <p id="title-footer" class="has-text-orange is-size-6 has-text-weight-medium">SERVICIOS</p>
            <div class="columns pt-3">
              <div v-for="(group, group_key) of services" :key="group_key" class="column">
                <ul class="is-size-7">
                  <li v-for="(service_group, service_group_key) of group" :key="service_group_key" class="pl-5">
                    <NuxtLink v-for="(service, service_key) of service_group" :key="service_key" :to="service.to">
                      <p class="is-size-7 pb-1">{{ service.title }}</p>
                    </NuxtLink> 
                  </li>
                </ul>
              </div>
            </div>
          </div>
          <div class="column is-half">
            <div class="columns is-multiline">
              <div class="column is-full">
                <div class="columns">  
                  <div class="column is-half is-flex">
                    <p id="title-footer" class="has-text-weight-semibold">JUMASE Informática</p>
                  </div>
                  <div class="column is-half is-flex is-justify-content-end">
                    <a href="https://www.facebook.com/jumaseinformatica" target="_blank">
                      <span class="ml-5 is-size-5">
                        <fa-icon :icon="faFacebook" />
                      </span>
                    </a>
                    <a href="https://whats.jumase.com.mx/" target="_blank">
                      <span class="ml-5 is-size-5">
                        <fa-icon :icon="faWhatsapp" />
                      </span>
                    </a>
                    <a href="https://www.youtube.com/channel/UCAbvXkSONtoRkIPtQAAfS6Q" target="_blank">
                      <span class="ml-5 is-size-5">
                        <fa-icon :icon="faYoutube" />
                      </span>
                    </a>
                  </div>
                </div>
              </div>
              <div class="column is-full">
                <p class="has-text-centered has-text-orange">¡Si la solución o producto que buscas no está listado en nuestro sitio, contáctanos y te lo conseguimos!</p>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="hero">
        <div class="hero-body p-0 pb-4">
          <p class="has-text-centered is-size-7">© 2022 JUMASE Informática by <span class="has-text-orange">Tony Piña</span></p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
  import { faFacebook, faWhatsapp, faYoutube } from '@fortawesome/free-brands-svg-icons'

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
        services: [
          {
            // nombre: 'TIC',
            group_1: [
              {
                title: 'Comunicaciones',
                to: {
                  name: 'servicios/comunicaciones'
                }
              },
              {
                title: 'Monitoreo de Red',
                to: {
                  name: 'servicios/monitoreo-de-red'
                }
              },
              {
                title: 'Telefonía',
                to: {
                  name: 'servicios/telefonia'
                }
              },
            ],
          },
          {
            // title: 'Seguridad',
            group_2: [
              {
                title: 'Ciberseguridad',
                to: {
                  name: 'servicios/ciberseguridad'
                }
              },
              {
                title: 'Seguridad Física',
                to: {
                  name: 'servicios/seguridad-fisica'
                }
              },
              {
                title: 'Respaldo',
                to: {
                  name: 'servicios/respaldo'
                }
              },
            ],
          },
          {
            // title: 'Software',
            group_3: [
              {
                title: 'Desarrollo Web',
                to: {
                  name: 'servicios/desarrollo-web'
                }
              },
              {
                title: 'Microsoft y Linux',
                to: {
                  name: 'servicios/microsoft-y-linux'
                }
              },
              {
                title: 'Virtualización',
                to: {
                  name: 'servicios/virtualizacion'
                }
              },
            ],
          },
          {
            // name: 'Otros'
            group_4: [
              {
                title: 'Cableado Estructurado',
                to: {
                  name: 'servicios/cableado-estructurado'
                }
              },
              {
                title: 'Servicios Administrados',
                to: {
                  name: 'servicios/servicios-administrados'
                }
              },
              {
                title: 'Soporte',
                to: {
                  name: 'servicios/soporte'
                }
              }
            ]
          }
        ]
      }
    },

    computed: {
      faFacebook () {
        return faFacebook
      },

      faWhatsapp () {
        return faWhatsapp
      },

      faYoutube () {
        return faYoutube
      }
    },
  }

</script>

<style lang="scss" scoped>

</style>

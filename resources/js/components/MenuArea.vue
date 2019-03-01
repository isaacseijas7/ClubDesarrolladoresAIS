<template>
  <div class="menu-area">
    <div class="top-menu-area">
      <div class="container">
        <div class="row">

          <div class="col-lg-3 col-md-3 col-6 v_middle">
            <div class="logo">
              <router-link :to="{ name: 'welcome' }">
                <img :src="imgLogo" alt="logo image" class="img-fluid">
              </router-link>
            </div>
          </div>

          <div class="col-lg-8 offset-lg-1 col-md-9 col-6 v_middle">

            <div v-if="user" class="author-area">
              <div class="author-author__info inline has_dropdown">
                <div class="author__avatar">
                  <img :src="imgAvatar" alt="user avatar">

                </div>
                <div class="autor__info">
                  <p class="name">
                    {{ user.name }}
                  </p>
                  <p class="ammount"></p>
                </div>

                <div class="dropdown dropdown--author">
                  <ul>
                    <li>
                      <router-link :to="{ name: 'home' }">
                        <span class="lnr lnr-home"></span> Escritorio
                      </router-link>
                    </li>
                    <li>
                      <router-link :to="{ name: 'settings.profile' }">
                        <span class="lnr lnr-user"></span> Perfil
                      </router-link>
                    </li>
                    <li>
                      <router-link :to="{ name: 'settings.password' }">
                        <span class="lnr lnr-cog"></span> Configuraciones
                      </router-link>
                    </li>
                    <li>
                      <a href="#" @click.prevent="logout">
                        <span class="lnr lnr-exit"></span>Cerrar Sesión
                      </a>
                    </li>
                  </ul>
                </div>
              </div>
            </div>

            <div v-if="!user" class="author-area not_logged_in">
              <div class="pull-right join">
                <router-link :to="{ name: 'register' }" class="btn btn--round btn-secondary  btn--xs">Crear cuenta</router-link>
                <router-link :to="{ name: 'login' }" class="btn btn--round btn--xs">Ingresar</router-link>
              </div>
            </div>

          </div>
        </div>
      </div>
    </div>

    <div class="mainmenu">
      <div class="container">
        <div class="row">
          <div class="col-md-12">

            <div class="navbar-header">
              <div class="mainmenu__search">
                <form action="#">
                  <div class="searc-wrap">
                    <input type="text" placeholder="Buscar...">
                    <button type="submit" class="search-wrap__btn">
                      <span class="lnr lnr-magnifier"></span>
                    </button>
                  </div>
                </form>
              </div>
            </div>

            <nav class="navbar navbar-expand-md navbar-light mainmenu__menu">
              <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false"
                  aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
              </button>

              <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav">
                  <li>
                    <router-link :to="{ name: 'welcome' }" active-class="active">INICIO</router-link>
                  </li>
                  <li>
                    <router-link :to="{ name: 'welcome' }" active-class="active">ACERCA</router-link>
                  </li>
                  <li>
                    <router-link :to="{ name: 'welcome' }" active-class="active">EVENTOS</router-link>
                  </li>
                  <li>
                    <router-link :to="{ name: 'welcome' }" active-class="active">BLOG</router-link>
                  </li>
                  <li>
                    <router-link :to="{ name: 'welcome' }" active-class="active">GALERÍA</router-link>
                  </li>
                  <li>
                    <router-link :to="{ name: 'welcome' }" active-class="active">CONTACTOS</router-link>
                  </li>
                </ul>
              </div>

            </nav>

          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>

const imgLogo = require('./../../images/logo.png');
const imgAvatar = require('./../../images/usr_avatar.png')

import { mapGetters } from 'vuex'

export default {
  components: { },

  data: () => ({
    appName: window.config.appName,
    imgLogo: imgLogo,
    imgAvatar: imgAvatar
  }),

  computed: mapGetters({
    user: 'auth/user'
  }),

  mounted() {
    this.main();
  },

  methods: {

    main (){
      console.log(this.imgLogo);
    },

    async logout () {
      // Log out the user.
      await this.$store.dispatch('auth/logout')

      // Redirect to login.
      this.$router.push({ name: 'login' })
    }
  }
}
</script>

<style scoped>

</style>

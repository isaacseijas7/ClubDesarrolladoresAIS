<template>
  <div>
    <section class="breadcrumb-area">
        <div class="container">
            <div class="row">
                <div class="col-md-12">
                    <div class="breadcrumb">
                        <ul>
                            <li>
                                <a href="index.html">Home</a>
                            </li>
                            <li>
                                <a href="dashboard.html">Escritorio</a>
                            </li>
                        </ul>
                    </div>
                    <h1 class="page-title">Escritorio</h1>
                </div>
            </div>
        </div>
    </section>
    <section class="dashboard-area">
        <div class="dashboard_menu_area">
            <div class="container">
                <div class="row">
                    <div class="col-md-12">
                        <ul class="dashboard_menu">
                            <li>
                                <router-link :to="{ name: 'home' }" active-class="active">
                                    <span class="lnr lnr-home"></span>Escritorio
                                </router-link>
                            </li>
                            <li>
                                <router-link :to="{ name: 'settings.profile' }" active-class="active">
                                  <span class="lnr lnr-cog"></span>Perfil
                                </router-link>
                            </li>
                            <li>
                                <router-link :to="{ name: 'settings.password' }" active-class="active">
                                  <span class="lnr lnr-cog"></span>Configuraciones
                                </router-link>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
        <div class="dashboard_contents">
            <div class="container">
              <transition name="fade" mode="out-in">
                <router-view/>
              </transition>
            </div>
        </div>
    </section>

    <!-- <div class="col-md-3">
      <card :title="$t('settings')" class="settings-card">
        <ul class="nav flex-column nav-pills">
          <li v-for="tab in tabs" :key="tab.route" class="nav-item">
            <router-link :to="{ name: tab.route }" class="nav-link" active-class="active">
              <fa :icon="tab.icon" fixed-width/>
              {{ tab.name }}

          </li>
        </ul>
      </card>
    </div> -->
  </div>
</template>

<script>
export default {
  middleware: 'auth',
  layout: 'basic',

  computed: {
    tabs () {
      return [
        {
          icon: 'user',
          name: this.$t('profile'),
          route: 'settings.profile'
        },
        {
          icon: 'lock',
          name: this.$t('password'),
          route: 'settings.password'
        }
      ]
    }
  }
}
</script>

<style>
.settings-card .card-body {
  padding: 0;
}
</style>

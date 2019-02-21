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
                <div class="row">
                    <div class="col-lg-3 col-md-6">
                        <div class="author-info author-info--dashboard mcolorbg4">
                            <p>Total Items</p>
                            <h3>4,369</h3>
                        </div>
                    </div>

                    <div class="col-lg-3 col-md-6">
                        <div class="author-info author-info--dashboard mcolorbg2">
                            <p>Monthly Sales</p>
                            <h3>$273.00</h3>
                        </div>
                    </div>

                    <div class="col-lg-3 col-md-6">
                        <div class="author-info author-info--dashboard mcolorbg3">
                            <p>Yearly Sales</p>
                            <h3>$2,249.00</h3>
                        </div>
                    </div>

                    <div class="col-lg-3 col-md-6">
                        <div class="author-info author-info--dashboard mcolorbg1">
                            <p>Lifetime Sales</p>
                            <h3>$5,583.00</h3>
                        </div>
                    </div>
                </div>
                <div class="row">
                  <div class="col-md-12">
                    {{ $t('you_are_logged_in') }}
                  </div>
                </div>
            </div>
        </div>
    </section>
  </div>
</template>

<script>
export default {
  middleware: 'auth',

  layout: 'basic',

  metaInfo () {
    return { title: this.$t('home') }
  }
}
</script>


<style scoped>
  .dashboard_menu_area .dashboard_menu li a.active {
      color: #0674ec;
  }
</style>

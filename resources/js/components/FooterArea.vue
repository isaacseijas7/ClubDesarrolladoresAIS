<template>
    <footer class="footer-area">
        <div class="mini-footer">
            <div class="container">
                <div class="row">
                    <div class="col-md-12">
                        <div class="copyright-text">
                            <p>&copy; {{ year }}
                                <router-link :to="{ name: 'welcome' }">{{ appName }}</router-link>. Todos los derechos reservados. Creado por
                                <a href="http://ais.unerg.edu.ve/" target="_black">AIS UNERG</a>
                            </p>
                        </div>

                        <div class="go_top">
                            <span class="lnr lnr-chevron-up"></span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  components: { },

  data: () => ({
    appName: window.config.appName,
    year: '2019'
  }),

  mounted() {
    this.main();
  },

  methods: {
    main() {
      var date = new Date();
      this.year = date.getFullYear();

      var scrollTop = $('.go_top');
      scrollTop.on('click', function () {
          $('html, body').animate({ scrollTop: 0 }, 800);
          return false;
      });

    },
  }
}
</script>

<style scoped>

</style>

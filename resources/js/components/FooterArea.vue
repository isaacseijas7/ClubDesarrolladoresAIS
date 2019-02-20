<template>
    <footer class="footer-area">
        <div class="footer-big section--padding">
            <div class="container">
                <div class="row">
                    <div class="col-lg-3 col-md-6">
                        <div class="info-footer">
                            <div class="info__logo">
                                <img src="images/logo.png" alt="footer logo">
                            </div>
                            <p class="info--text">Nunc placerat mi id nisi interdum they mollis. Praesent pharetra, justo ut scel erisque the mattis,
                                leo quam.</p>
                            <ul class="info-contact">
                                <li>
                                    <span class="lnr lnr-phone info-icon"></span>
                                    <span class="info">Phone: +6789-875-2235</span>
                                </li>
                                <li>
                                    <span class="lnr lnr-envelope info-icon"></span>
                                    <span class="info">support@aazztech.com</span>
                                </li>
                                <li>
                                    <span class="lnr lnr-map-marker info-icon"></span>
                                    <span class="info">202 New Hampshire Avenue Northwest #100, New York-2573</span>
                                </li>
                            </ul>
                        </div>
                    </div>

                    <div class="col-lg-5 col-md-6">
                        <div class="footer-menu" style="width: 100%;">
                            <h4 class="footer-widget-title text--white">Our Company</h4>
                            <ul>
                                <li>
                                    <a href="#">How to Join Us</a>
                                </li>
                                <li>
                                    <a href="#">How It Work</a>
                                </li>
                                <li>
                                    <a href="#">Buying and Selling</a>
                                </li>
                                <li>
                                    <a href="#">Testimonials</a>
                                </li>
                                <li>
                                    <a href="#">Copyright Notice</a>
                                </li>
                                <li>
                                    <a href="#">Refund Policy</a>
                                </li>
                                <li>
                                    <a href="#">Affiliates</a>
                                </li>
                            </ul>
                        </div>
                    </div>


                    <div class="col-lg-4 col-md-12">
                        <div class="newsletter">
                            <h4 class="footer-widget-title text--white">Hoja informativa</h4>
                            <p>Suscríbete para recibir las últimas noticias, actualizaciones y ofertas de información. No te preocupes, ¡no enviaremos spam!</p>
                            <div class="newsletter__form">
                                <form action="#">
                                    <div class="field-wrapper">
                                        <input class="relative-field rounded" type="text" placeholder="Ingrese correo electrónico">
                                        <button class="btn btn--round" type="submit">Enviar</button>
                                    </div>
                                </form>
                            </div>


                            <div class="social social--color--filled">
                                <ul>
                                    <li>
                                        <a href="#">
                                            <span class="fa fa-facebook"></span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href="#">
                                            <span class="fa fa-twitter"></span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href="#">
                                            <span class="fa fa-google-plus"></span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href="#">
                                            <span class="fa fa-pinterest"></span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href="#">
                                            <span class="fa fa-linkedin"></span>
                                        </a>
                                    </li>
                                    <li>
                                        <a href="#">
                                            <span class="fa fa-dribbble"></span>
                                        </a>
                                    </li>
                                </ul>
                            </div>

                        </div>

                    </div>

                </div>

            </div>

        </div>


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

  computed: mapGetters({
    user: 'auth/user',
  }),

  mounted() {
    this.main();
  },

  methods: {
    main() {
      var date = new Date();
      this.year = date.getFullYear();
    },
  }
}
</script>

<style scoped>

</style>

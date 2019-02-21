<template>
  <div>
    <section class="about_hero bgimage">
        <div class="bg_image_holder">
            <img src="images/inicio.jpg" alt="">
        </div>

        <div class="container content_above">
            <div class="row">
                <div class="col-md-12">
                    <div class="about_hero_contents">
                        <h1>Club {{ title }}</h1>
                        <p>Área de Ingeniería Sistemas</p>
                        <p style="line-height: 10px; font-size: 18px;">Cada día somos más</p>

                        <div v-if="!authenticated" class="about_hero_btns">
                          <router-link :to="{ name: 'register' }" class="btn btn--round btn--lg">Quiero unirme</router-link>
                          <router-link :to="{ name: 'login' }" class="btn btn--white btn--lg btn--round">Ingresar</router-link>
                        </div>

                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="about_mission">
        <div class="content_block1">
            <div class="container">
                <div class="row">
                    <div class="col-md-5 col-sm-12">
                        <div class="content_area">
                            <h1 class="content_area--title">Acerca
                                <span class="highlight">{{ title }}</span>
                            </h1>
                            <p>
                              Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
                              tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
                              quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
                              consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
                              cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                              proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                            </p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="content_image bgimage">
                <div class="bg_image_holder">
                    <img src="images/ab1.jpg" alt="">
                </div>
            </div>
        </div>

        <div class="content_block2">
            <div class="container">
                <div class="row">
                    <div class="col-lg-5 col-md-6  offset-md-6 offset-lg-7">
                        <div class="content_area2">
                            <h1 class="content_area2--title">{{ title }}
                                <span class="highlight">Misión</span>
                            </h1>
                            <p>
                              Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
                              tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
                              quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
                              consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
                              cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                              proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                            </p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="content_image2 bgimage">
                <div class="bg_image_holder">
                    <img src="images/ab2.jpg" alt="">
                </div>
            </div>
        </div>
    </section>

    <section class="team_area section--padding">
        <div class="container">
            <div class="row">
                <div class="col-md-12">
                    <div class="section-title">
                        <h1>El equipo
                            <span class="highlighted">{{ title }}</span>
                        </h1>
                        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
                        tempor incididunt ut labore et dolore magna aliqua.</p>
                    </div>
                </div>
            </div>


            <div class="row">
                <div class="col-lg-3 col-md-4">
                    <div class="single_team_member">
                        <figure>
                            <img src="images/team1.jpg" alt="Team Member">
                            <figcaption>
                                <div class="name_desig">
                                    <h4>Douglus Khundu</h4>
                                    <p>Software Engineer</p>
                                </div>


                                <div class="social">
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
                                                <span class="fa fa-dribbble"></span>
                                            </a>
                                        </li>
                                    </ul>
                                </div>

                            </figcaption>

                        </figure>

                    </div>

                </div>


                <div class="col-lg-3 col-md-4">
                    <div class="single_team_member">
                        <figure>
                            <img src="images/team2.jpg" alt="Team Member">
                            <figcaption>
                                <div class="name_desig">
                                    <h4>Robert Jellybean</h4>
                                    <p>Application Developer</p>
                                </div>

                                <div class="social">
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
                                                <span class="fa fa-dribbble"></span>
                                            </a>
                                        </li>
                                    </ul>
                                </div>

                            </figcaption>

                        </figure>

                    </div>

                </div>


                <div class="col-lg-3 col-md-4">
                    <div class="single_team_member">
                        <figure>
                            <img src="images/team3.jpg" alt="Team Member">
                            <figcaption>
                                <div class="name_desig">
                                    <h4>Tomat Notfrut</h4>
                                    <p>Js Developer</p>
                                </div>


                                <div class="social">
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
                                                <span class="fa fa-dribbble"></span>
                                            </a>
                                        </li>
                                    </ul>
                                </div>

                            </figcaption>

                        </figure>

                    </div>

                </div>


                <div class="col-lg-3 col-md-4">
                    <div class="single_team_member">
                        <figure>
                            <img src="images/team4.jpg" alt="Team Member">
                            <figcaption>
                                <div class="name_desig">
                                    <h4>Naro Sundor</h4>
                                    <p>CTO</p>
                                </div>


                                <div class="social">
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
                                                <span class="fa fa-dribbble"></span>
                                            </a>
                                        </li>
                                    </ul>
                                </div>

                            </figcaption>

                        </figure>

                    </div>

                </div>


                <div class="col-lg-3 col-md-4">
                    <div class="single_team_member">
                        <figure>
                            <img src="images/team2.jpg" alt="Team Member">
                            <figcaption>
                                <div class="name_desig">
                                    <h4>Robert Jellybean</h4>
                                    <p>Application Developer</p>
                                </div>


                                <div class="social">
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
                                                <span class="fa fa-dribbble"></span>
                                            </a>
                                        </li>
                                    </ul>
                                </div>

                            </figcaption>

                        </figure>

                    </div>

                </div>


                <div class="col-lg-3 col-md-4">
                    <div class="single_team_member">
                        <figure>
                            <img src="images/team3.jpg" alt="Team Member">
                            <figcaption>
                                <div class="name_desig">
                                    <h4>Tomat Notfrut</h4>
                                    <p>Js Developer</p>
                                </div>


                                <div class="social">
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
                                                <span class="fa fa-dribbble"></span>
                                            </a>
                                        </li>
                                    </ul>
                                </div>

                            </figcaption>

                        </figure>

                    </div>

                </div>


                <div class="col-lg-3 col-md-4">
                    <div class="single_team_member">
                        <figure>
                            <img src="images/team4.jpg" alt="Team Member">
                            <figcaption>
                                <div class="name_desig">
                                    <h4>Naro Sundor</h4>
                                    <p>CTO</p>
                                </div>


                                <div class="social">
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
                                                <span class="fa fa-dribbble"></span>
                                            </a>
                                        </li>
                                    </ul>
                                </div>

                            </figcaption>

                        </figure>

                    </div>

                </div>


                <div class="col-lg-3 col-md-4">
                    <div class="single_team_member">
                        <figure>
                            <img src="images/team1.jpg" alt="Team Member">
                            <figcaption>
                                <div class="name_desig">
                                    <h4>Douglus Khundu</h4>
                                    <p>Software Engineer</p>
                                </div>


                                <div class="social">
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
                                                <span class="fa fa-dribbble"></span>
                                            </a>
                                        </li>
                                    </ul>
                                </div>

                            </figcaption>

                        </figure>

                    </div>

                </div>

            </div>

        </div>
    </section>

    <section class="gallery_area">
        <div class="gallery_contents_wrapper bgimage">
            <div class="bg_image_holder">
                <img src="images/galbg.jpg" alt="">
            </div>
            <div class="container content_above">
                <div class="row">
                    <div class="col-md-6 offset-md-3">
                        <div class="gallery_contents">
                            <h3>{{ title }}</h3>
                            <p>Amamos lo que hacemos y vivimos todos los días con pasión para cambiar el mundo</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="call-to-action bgimage">
        <div class="bg_image_holder">
            <img src="images/calltobg.jpg" alt="">
        </div>
        <div class="container content_above">
            <div class="row">
                <div class="col-md-12">
                    <div class="call-to-wrap">
                        <h1 class="text--white">¿Estas listo para unirse a nuestro Club?</h1>
                        <h4 class="text--white">{{ title }} Cada día somos más</h4>
                        <router-link :to="{ name: 'register' }" class="btn btn--lg btn--round btn--white callto-action-btn">
                          si quiero unirme
                        </router-link>
                    </div>
                </div>
            </div>
        </div>
    </section>

  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  layout: 'basic',

  metaInfo () {
    return { title: this.$t('home') }
  },

  data: () => ({
    title: window.config.appName
  }),

  computed: mapGetters({
    authenticated: 'auth/check',
  }),

  mounted() {
    this.main();
  },

  methods: {
    async logout () {
      // Log out the user.
      await this.$store.dispatch('auth/logout')

      // Redirect to login.
      this.$router.push({ name: 'login' })
    },
    main() {
      $('.bg_image_holder').each(function () {
          var $this = $(this);
          var imgLink = $this.children().attr('src');
          $this.css({
              "background-image": "url(" + imgLink + ")",
              "opacity": "1"
          }).children().attr('alt', imgLink);
      });
    }
  }

}
</script>

<style scoped>

</style>

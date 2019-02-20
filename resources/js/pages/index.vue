<template>
  <div>
    <section class="hero-area bgimage">
      <div class="bg_image_holder">
        <img src="images/hero_area_bg1.jpg" alt="background-image">
      </div>
      <div class="hero-content content_above">
        <div class="content-wrapper">
          <div class="container">
            <div class="row">
              <div class="col-md-12">
                <div class="hero__content__title">
                  <h1>
                    <span class="light">Club de Desarrolladores AIS</span>
                    <span class="bold">Área de Ingeniería Sistemas</span>
                  </h1>
                  <p class="tagline"></p>
                </div>
                <div v-if="!authenticated" class="hero__btn-area">
                  <router-link :to="{ name: 'register' }" class="btn btn--round btn--lg">Crear cuenta</router-link>
                  <router-link :to="{ name: 'login' }" class="btn btn--round btn--lg">Ingresar</router-link>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="search-area">
        <div class="container">
            <div class="row">
                <div class="col-sm-12">
                    <div class="search_box">
                        <form action="#">
                            <input type="text" class="text_field" placeholder="Search your products...">
                            <div class="search__select select-wrap">
                                <select name="category" class="select--field" id="blah">
                                    <option value="">All Categories</option>
                                    <option value="">PSD</option>
                                    <option value="">HTML</option>
                                    <option value="">WordPress</option>
                                    <option value="">All Categories</option>
                                </select>
                                <span class="lnr lnr-chevron-down"></span>
                            </div>
                            <button type="submit" class="search-btn btn--lg">Search Now</button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
      </div>

    </section>

    <section class="features section--padding">
        <div class="container">
            <div class="row">
                <div class="col-lg-4 col-md-6">
                    <div class="feature">
                        <div class="feature__img">
                            <img src="images/feature1.png" alt="feature">
                        </div>
                        <div class="feature__title">
                            <h3>Best UX Research</h3>
                        </div>
                        <div class="feature__desc">
                            <p>Nunc placerat mi id nisi interdum mollis. Praesent pharetra, justo ut scelerisque the mattis,
                                leo quam aliquet diam congue is laoreet elit metus.</p>
                        </div>
                    </div>
                </div>

                <div class="col-lg-4 col-md-6">
                    <div class="feature">
                        <div class="feature__img">
                            <img src="images/feature2.png" alt="feature">
                        </div>
                        <div class="feature__title">
                            <h3>Fully Responsive</h3>
                        </div>
                        <div class="feature__desc">
                            <p>Nunc placerat mi id nisi interdum mollis. Praesent pharetra, justo ut scelerisque the mattis,
                                leo quam aliquet diam congue is laoreet elit metus.</p>
                        </div>
                    </div>
                </div>

                <div class="col-lg-4 col-md-6">
                    <div class="feature">
                        <div class="feature__img">
                            <img src="images/feature3.png" alt="feature">
                        </div>
                        <div class="feature__title">
                            <h3>Buy & Sell Easily</h3>
                        </div>
                        <div class="feature__desc">
                            <p>Nunc placerat mi id nisi interdum mollis. Praesent pharetra, justo ut scelerisque the mattis,
                                leo quam aliquet diam congue is laoreet elit metus.</p>
                        </div>
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

  methods: {
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

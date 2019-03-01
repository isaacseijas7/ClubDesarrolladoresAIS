<template>
  <div>
    <section class="breadcrumb-area">
      <div class="container">
        <div class="row">
          <div class="col-md-12">
            <div class="breadcrumb">
              <ul>
                <li>
                    <router-link :to="{ name: 'welcome' }">Inicio</router-link>
                </li>
                <li class="active">
                    <router-link :to="{ name: 'login' }">Ingresar</router-link>
                </li>
              </ul>
            </div>
            <h1 class="page-title">Ingresar</h1>
          </div>
        </div>
      </div>
    </section>
    <section class="login_area section--padding2">
        <div class="container">
            <div class="row">
                <div class="col-lg-6 offset-lg-3">
                    <form @submit.prevent="login" @keydown="form.onKeydown($event)">
                        <div class="cardify login">
                            <div class="login--header">
                                <h3>Bienvenido</h3>
                                <p>Puedes iniciar sesión con tu correo electrónico y contraseña</p>
                            </div>

                            <div class="login--form">
                                <div class="form-group">
                                    <label for="email">{{ $t('email') }}</label>

                                    <input v-model="form.email" :class="{ 'is-invalid': form.errors.has('email') }" class="form-control text_field" :placeholder="$t('email')" type="email" name="email" id="email" autofocus>
                                    <has-error :form="form" field="email"/>

                                </div>

                                <div class="form-group">
                                    <label for="password">{{ $t('password') }}</label>
                                    <input v-model="form.password" :class="{ 'is-invalid': form.errors.has('password') }" class="form-control text_field" :placeholder="$t('password')" type="password" name="password" id="password">
                                    <has-error :form="form" field="password"/>
                                </div>

                                <div class="form-group">
                                    <div class="custom_checkbox">
                                        <checkbox v-model="remember" id="ch2" name="remember">
                                          {{ $t('remember_me') }}
                                        </checkbox>
                                    </div>
                                </div>

                                <v-button class="btn btn--md btn--round" :loading="form.busy">
                                  {{ $t('login') }}
                                </v-button>

                                <!-- GitHub Login Button -->
                                <login-with-github/>

                                <div class="login_assist">

                                    <router-link :to="{ name: 'password.request' }" class="recover">
                                      {{ $t('forgot_password') }}
                                    </router-link>

                                    <p class="signup">¿No tienes una
                                        <router-link :to="{ name: 'register' }">cuenta</router-link>?</p>
                                </div>
                            </div>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </section>
  </div>
</template>

<script>
import Form from 'vform'
import LoginWithGithub from '~/components/LoginWithGithub'

export default {
  middleware: 'guest',
  layout: 'basic',

  components: {
    LoginWithGithub
  },

  metaInfo () {
    return { title: this.$t('login') }
  },

  data: () => ({
    form: new Form({
      email: '',
      password: ''
    }),
    remember: false
  }),

  methods: {
    async login () {
      // Submit the form.
      const { data } = await this.form.post('/api/login')

      // Save the token.
      this.$store.dispatch('auth/saveToken', {
        token: data.token,
        remember: this.remember
      })

      // Fetch the user.
      await this.$store.dispatch('auth/fetchUser')

      // Redirect home.
      this.$router.push({ name: 'settings.profile' })
    }
  }
}
</script>

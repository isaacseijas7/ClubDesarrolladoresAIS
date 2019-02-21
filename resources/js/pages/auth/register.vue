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
                                <router-link :to="{ name: 'welcome' }">Crear cuenta</router-link>
                            </li>
                        </ul>
                    </div>
                    <h1 class="page-title">Crear cuenta</h1>
                </div>
            </div>
        </div>
    </section>
    <section class="signup_area section--padding2">
        <div class="container">
            <div class="row">
                <div class="col-lg-6 offset-lg-3">
                    <form @submit.prevent="register" @keydown="form.onKeydown($event)">
                        <div class="cardify signup_form">
                            <div class="login--header">
                                <h3>Crea tu cuenta</h3>
                                <p>Por favor llene los siguientes campos con información apropiada</p>
                            </div>

                            <div class="login--form">

                                <div class="form-group">
                                    <label for="name">{{ $t('name') }}</label>

                                    <input v-model="form.name" :class="{ 'is-invalid': form.errors.has('name') }" class="form-control text_field" :placeholder="$t('name')" type="text" name="name" id="name" autofocus>
                                    <has-error :form="form" field="name"/>

                                </div>

                                <div class="form-group">
                                    <label for="email">{{ $t('email') }}</label>

                                    <input v-model="form.email" :class="{ 'is-invalid': form.errors.has('email') }" class="form-control text_field" :placeholder="$t('email')" type="email" name="email" id="email">
                                    <has-error :form="form" field="email"/>

                                </div>

                                <div class="form-group">
                                    <label for="password">{{ $t('password') }}</label>
                                    <input v-model="form.password" :class="{ 'is-invalid': form.errors.has('password') }" class="form-control text_field" :placeholder="$t('password')" type="password" name="password" id="password">
                                    <has-error :form="form" field="password"/>
                                </div>

                                <div class="form-group">
                                    <label for="password_confirmation">{{ $t('confirm_password') }}</label>
                                    <input v-model="form.password_confirmation" :class="{ 'is-invalid': form.errors.has('password_confirmation') }" class="form-control text_field" :placeholder="$t('confirm_password')" type="password" name="password_confirmation" id="password_confirmation">
                                    <has-error :form="form" field="password_confirmation"/>
                                </div>

                                <v-button class="btn btn--md btn--round register_btn" :loading="form.busy">
                                  {{ $t('register') }}
                                </v-button>

                                <!-- GitHub Register Button -->
                                <login-with-github/>

                                <div class="login_assist">
                                    <p>¿Ya tengo una cuenta?
                                        <router-link :to="{ name: 'login' }">Ingresar</router-link>
                                    </p>
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
    return { title: this.$t('register') }
  },

  data: () => ({
    form: new Form({
      name: '',
      email: '',
      password: '',
      password_confirmation: ''
    })
  }),

  methods: {
    async register () {
      // Register the user.
      const { data } = await this.form.post('/api/register')

      // Log in the user.
      const { data: { token } } = await this.form.post('/api/login')

      // Save the token.
      this.$store.dispatch('auth/saveToken', { token })

      // Update the user.
      await this.$store.dispatch('auth/updateUser', { user: data })

      // Redirect home.
      this.$router.push({ name: 'home' })
    }
  }
}
</script>

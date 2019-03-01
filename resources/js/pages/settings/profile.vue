<template>
  <div class="row">
      <div class="col-md-12">
        <div class="dashboard_title_area">
          <div class="dashboard__title">
              <h3>Account Settings</h3>
          </div>
        </div>
      </div>

      <div class="setting_form">
          <div class="row">
              <div class="col-lg-6">
                  <div class="information_module">
                      <a class="toggle_title" href="#collapse2" role="button" data-toggle="collapse" aria-expanded="false" aria-controls="collapse1">
                          <h4>Personal Information
                              <span class="lnr lnr-chevron-down"></span>
                          </h4>
                      </a>

                      <form @submit.prevent="update" @keydown="form.onKeydown($event)">

                        <alert-success :form="form" :message="$t('info_updated')"/>

                        <div class="information__set toggle_module collapse show" id="collapse2">
                            <div class="information_wrapper form--fields">
                                <div class="form-group">
                                    <label for="name">{{ $t('name') }}
                                        <sup>*</sup>
                                    </label>
                                    <input v-model="form.name" :placeholder="$t('name')" :class="{ 'is-invalid': form.errors.has('name') }" class="form-control text_field" type="text" name="name" id="name">
                                    <has-error :form="form" field="name"/>
                                </div>

                                <div class="form-group">
                                    <label for="email">{{ $t('email') }}
                                        <sup>*</sup>
                                    </label>
                                    <input v-model="form.email" :placeholder="$t('email')" :class="{ 'is-invalid': form.errors.has('email') }" class="form-control text_field" type="email" name="email" id="email">
                                    <has-error :form="form" field="email"/>
                                </div>
                                <div class="dashboard_setting_btn">
                                    <v-button :loading="form.busy" type="success" class="btn btn--round btn--md">{{ $t('update') }}</v-button>
                                </div>

                            </div>

                        </div>

                      </form>

                  </div>


                  <div class="information_module">
                      <a class="toggle_title" href="#collapse1" role="button" data-toggle="collapse" aria-expanded="false" aria-controls="collapse1">
                          <h4>Biling Information
                              <span class="lnr lnr-chevron-down"></span>
                          </h4>
                      </a>

                      <div class="information__set toggle_module collapse" id="collapse1">
                          <div class="information_wrapper form--fields">
                              <div class="row">
                                  <div class="col-md-6">
                                      <div class="form-group">
                                          <label for="first_name">First Name
                                              <sup>*</sup>
                                          </label>
                                          <input type="text" id="first_name" class="text_field" placeholder="First Name" value="Ron">
                                      </div>
                                  </div>

                                  <div class="col-md-6">
                                      <div class="form-group">
                                          <label for="last_name">last Name
                                              <sup>*</sup>
                                          </label>
                                          <input type="text" id="last_name" class="text_field" placeholder="last name" value="Doe">
                                      </div>
                                  </div>
                              </div>


                              <div class="form-group">
                                  <label for="email">Company Name
                                      <sup>*</sup>
                                  </label>
                                  <input type="text" id="email" class="text_field" placeholder="AazzTech" value="AazzTech">
                              </div>

                              <div class="form-group">
                                  <label for="email1">Email Adress
                                      <sup>*</sup>
                                  </label>
                                  <input type="text" id="email1" class="text_field" placeholder="Email address" value="contact@aazztech.com">
                              </div>

                              <div class="form-group">
                                  <label for="country1">Country
                                      <sup>*</sup>
                                  </label>
                                  <div class="select-wrap select-wrap2">
                                      <select name="country" id="country" class="text_field">
                                          <option value="">Select one</option>
                                          <option value="bangladesh">Bangladesh</option>
                                          <option value="india">India</option>
                                          <option value="uruguye">Uruguye</option>
                                          <option value="australia">Australia</option>
                                          <option value="neverland">Neverland</option>
                                          <option value="atlantis">Atlantis</option>
                                      </select>
                                      <span class="lnr lnr-chevron-down"></span>
                                  </div>
                              </div>


                              <div class="form-group">
                                  <label for="address1">Address Line 1</label>
                                  <input type="text" id="address1" class="text_field" placeholder="Address line one">
                              </div>

                              <div class="form-group">
                                  <label for="address2">Address Line 2</label>
                                  <input type="text" id="address2" class="text_field" placeholder="Address line two">
                              </div>

                              <div class="row">
                                  <div class="col-md-6">
                                      <div class="form-group">
                                          <label for="city">City / State
                                              <sup>*</sup>
                                          </label>
                                          <div class="select-wrap select-wrap2">
                                              <select name="city" id="city" class="text_field">
                                                  <option value="">Select one</option>
                                                  <option value="dhaka">Dhaka</option>
                                                  <option value="sydney">Sydney</option>
                                                  <option value="newyork">New York</option>
                                                  <option value="london">London</option>
                                                  <option value="mexico">New Mexico</option>
                                              </select>
                                              <span class="lnr lnr-chevron-down"></span>
                                          </div>
                                      </div>
                                  </div>
                                  <div class="col-md-6">
                                      <div class="form-group">
                                          <label for="zipcode">Zip / Postal Code
                                              <sup>*</sup>
                                          </label>
                                          <input type="text" id="zipcode" class="text_field" placeholder="zip/postal code">
                                      </div>
                                  </div>
                              </div>
                          </div>
                      </div>

                  </div>

              </div>

              <div class="col-lg-6">
                  <div class="information_module">
                      <a class="toggle_title" href="#collapse3" role="button" data-toggle="collapse" aria-expanded="false" aria-controls="collapse1">
                          <h4>Profile Image & Cover
                              <span class="lnr lnr-chevron-down"></span>
                          </h4>
                      </a>

                      <div class="information__set profile_images toggle_module collapse" id="collapse3">
                          <div class="information_wrapper">
                              <div class="profile_image_area">
                                  <img src="images/authplc.png" alt="Author profile area">
                                  <div class="img_info">
                                      <p class="bold">Profile Image</p>
                                      <p class="subtitle">JPG, GIF or PNG 100x100 px</p>
                                  </div>

                                  <label for="cover_photo" class="upload_btn">
                                      <input type="file" id="cover_photo" style="width: 0; height: 0;">
                                      <span class="btn btn--sm btn--round" aria-hidden="true">Upload Image</span>
                                  </label>
                              </div>

                              <div class="prof_img_upload">
                                  <p class="bold">Cover Image</p>
                                  <img src="images/cvrplc.jpg" alt="The great warrior of China">

                                  <div class="upload_title">
                                      <p>JPG, GIF or PNG 750x370 px</p>
                                      <label for="dp" class="upload_btn">
                                          <input type="file" id="dp" style="width: 0; height: 0;">
                                          <span class="btn btn--sm btn--round" aria-hidden="true">Upload Image</span>
                                      </label>
                                  </div>
                              </div>
                          </div>
                      </div>
                  </div>


                  <div class="information_module">
                      <a class="toggle_title" href="#collapse5" role="button" data-toggle="collapse" aria-expanded="false" aria-controls="collapse1">
                          <h4>Social Profiles
                              <span class="lnr lnr-chevron-down"></span>
                          </h4>
                      </a>

                      <div class="information__set social_profile toggle_module collapse " id="collapse5">
                          <div class="information_wrapper">
                              <div class="social__single">
                                  <div class="social_icon">
                                      <span class="fa fa-facebook"></span>
                                  </div>

                                  <div class="link_field">
                                      <input type="text" class="text_field" placeholder="ex: www.facebook.com/aazztech">
                                  </div>
                              </div>


                              <div class="social__single">
                                  <div class="social_icon">
                                      <span class="fa fa-twitter"></span>
                                  </div>

                                  <div class="link_field">
                                      <input type="text" class="text_field" placeholder="ex: www.twitter.com/aazztech">
                                  </div>
                              </div>


                              <div class="social__single">
                                  <div class="social_icon">
                                      <span class="fa fa-google-plus"></span>
                                  </div>

                                  <div class="link_field">
                                      <input type="text" class="text_field" placeholder="ex: www.google.com/aazztech">
                                  </div>
                              </div>


                              <div class="social__single">
                                  <div class="social_icon">
                                      <span class="fa fa-behance"></span>
                                  </div>

                                  <div class="link_field">
                                      <input type="text" class="text_field" placeholder="ex: www.behance.com/aazztech">
                                  </div>
                              </div>


                              <div class="social__single">
                                  <div class="social_icon">
                                      <span class="fa fa-dribbble"></span>
                                  </div>

                                  <div class="link_field">
                                      <input type="text" class="text_field" placeholder="ex: www.dribbble.com/aazztech">
                                  </div>
                              </div>

                          </div>

                      </div>

                  </div>

                  <div class="information_module">
                      <a class="toggle_title" href="#collapse4" role="button" data-toggle="collapse" aria-expanded="false" aria-controls="collapse1">
                          <h4>Email Settings
                              <span class="lnr lnr-chevron-down"></span>
                          </h4>
                      </a>

                      <div class="information__set mail_setting toggle_module collapse" id="collapse4">
                          <div class="information_wrapper">
                              <div class="custom_checkbox">
                                  <input type="checkbox" id="opt1" class="" name="mail_rating_reminder" checked>
                                  <label for="opt1">
                                      <span class="shadow_checkbox"></span>
                                      <span class="radio_title">Rating Reminders</span>
                                      <span class="desc">Send an email reminding me to rate an item after purchase</span>
                                  </label>
                              </div>


                              <div class="custom_checkbox">
                                  <input type="checkbox" id="opt2" class="" name="mail_update_noti" checked>
                                  <label for="opt2">
                                      <span class="shadow_checkbox"></span>
                                      <span class="radio_title">Item Update Notifications</span>
                                      <span class="desc">Send an email when an item I've purchased is updated</span>
                                  </label>
                              </div>


                              <div class="custom_checkbox">
                                  <input type="checkbox" id="opt3" class="" name="mail_comment_noti" checked>
                                  <label for="opt3">
                                      <span class="shadow_checkbox"></span>
                                      <span class="radio_title">Item Comment Notifications</span>
                                      <span class="desc">Send me an email when someone comments on one of my items</span>
                                  </label>
                              </div>


                              <div class="custom_checkbox">
                                  <input type="checkbox" id="opt4" class="" name="mail_item_review_noti" checked>
                                  <label for="opt4">
                                      <span class="shadow_checkbox"></span>
                                      <span class="radio_title">Item Review Notifications</span>
                                      <span class="desc">Send me an email when my items are approved or rejected</span>
                                  </label>
                              </div>


                              <div class="custom_checkbox">
                                  <input type="checkbox" id="opt5" class="" name="mail_review_noti" checked>
                                  <label for="opt5">
                                      <span class="shadow_checkbox"></span>
                                      <span class="radio_title">Buyer Review Notifications</span>
                                      <span class="desc">Send me an email when someone leaves a review with their rating</span>
                                  </label>
                              </div>


                              <div class="custom_checkbox">
                                  <input type="checkbox" id="opt6" class="" name="mail_support_noti" checked>
                                  <label for="opt6">
                                      <span class="shadow_checkbox"></span>
                                      <span class="radio_title">Support Notifications</span>
                                      <span class="desc">Send me emails showing my soon to expire support entitlements</span>
                                  </label>
                              </div>


                              <div class="custom_checkbox">
                                  <input type="checkbox" id="opt7" class="" name="mail_weekly">
                                  <label for="opt7">
                                      <span class="shadow_checkbox"></span>
                                      <span class="radio_title">Weekly Summary Emails</span>
                                      <span class="desc">Send me emails showing my soon to expire support entitlements</span>
                                  </label>
                              </div>


                              <div class="custom_checkbox">
                                  <input type="checkbox" id="opt8" class="" name="mail_newsletter">
                                  <label for="opt8">
                                      <span class="shadow_checkbox"></span>
                                      <span class="radio_title">MartPlace Newsletter</span>
                                      <span class="desc">Get update about latest news, update and more.</span>
                                  </label>
                              </div>

                          </div>

                      </div>

                  </div>

              </div>

          </div>
      </div>

  </div>
</template>

<script>
import Form from 'vform'
import { mapGetters } from 'vuex'

export default {
  scrollToTop: false,

  metaInfo () {
    return { title: this.$t('settings') }
  },

  data: () => ({
    form: new Form({
      name: '',
      email: ''
    })
  }),

  computed: mapGetters({
    user: 'auth/user'
  }),

  created () {
    // Fill the form with user data.
    this.form.keys().forEach(key => {
      this.form[key] = this.user[key]
    })
  },

  methods: {
    async update () {
      const { data } = await this.form.patch('/api/settings/profile')

      this.$store.dispatch('auth/updateUser', { user: data })
    }
  }
}
</script>

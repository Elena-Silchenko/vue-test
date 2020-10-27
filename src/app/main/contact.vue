<template>
  <v-card class="mx-auto" style="width: 25em;">
    <v-form v-model="valid" ref="form" class="pa-5">  
      <v-text-field
        v-model="fullname"
        :rules="nameRules"
        label="Full name"
        required
      />
      <v-text-field
        v-model="email"
        :rules="emailRules"
        label="E-mail"
        required
      />
      <v-textarea
        solo
        auto-grow
        clearable
        clear-icon="mdi-close-circle"
        v-model="message"
        label="Your message"
      />
      <div class="g-recaptcha" data-sitekey="6Lcn3PQUAAAAAIeOA-Z5rk-0YRyhPXDiyohCfdSC" />
    </v-form>

    <v-divider />

    <v-card-actions>
      <v-btn
        text
        @click="$refs.form.reset()"
      >
        Clear
      </v-btn>
      <v-spacer></v-spacer>
      <v-btn
        :disabled="!valid"
        :loading="isLoading"
        class="white--text"
        color="deep-purple accent-4"
        depressed
      >
        Submit
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
  export default {
    data: () => ({
      valid: false,

      fullname: "",
      nameRules: [
        v => {
          if(v) return true
          return "Fullname is requred"
        },
        v => {
          if(v && v.length > 5) return true
          return "Fullname must be greater than 10 characters"
        },
      ],

      email: "",
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid',
      ],

      message: "",

      isLoading: false,
    })
}
</script>
<template>
  <div>
    <form>
      <div class="row">
        <div class="form-group">
          <label for="firstName">First Name</label>
          <input id="firstName" type="text" class="form-control" v-model="signupData.firstName">
        </div>
        <div class="form-group">
          <label for="lastName">Last Name</label>
          <input id="lastName" type="text" class="form-control" v-model="signupData.lastName">
        </div>
        <div class="form-group">
          <label for="mail">Mail</label>
          <input id="mail" type="text" class="form-control" v-model="signupData.mail">
        </div>
        <div class="form-group">
          <label for="password">Password</label>
          <input id="password" type="password" class="form-control" v-model="signupData.password">
        </div>
        <div class="form-group">
          <label>Store Data?</label>
          <input type="radio" value="Yes" v-model="signupData.storeData"> Yes
          <input type="radio" value="No" v-model="signupData.storeData"> No
        </div>
      </div>
      <div class="row">
        <button class="btn btn-primary" @click.prevent="signUp">Submit</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data () {
    return {
      signupData: {
        firstName: '',
        lastName: '',
        mail: '',
        password: '',
        storeData: ''
      }
    }
  },
  computed: {
    validation () {
      return {
        firstName: !!this.signupData.firstName.trim(),
        lastName: !!this.signupData.firstName.trim(),
        mail: !!this.signupData.mail.trim(),
        password: !!this.signupData.password.trim(),
        storeData: !!this.signupData.storeData.trim()
      }
    },
    isValid () {
      var validation = this.validation
      return Object.keys(validation).every(function (key) {
        return validation[key]
      })
    }
  },
  methods: {
    signUp () {
      if (this.isValid) {
        this.$emit('submitted', this.signupData)
      }
    }
  }
}
</script>

<style>
</style>
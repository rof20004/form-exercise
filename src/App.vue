<template>
    <div class="container">
        <form>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <signup-form @submitted="signupData = $event" v-if="!isSubmitted"></signup-form>
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="isSubmitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <full-name v-model="signupData"></full-name>
                        <p>Mail: {{ signupData.mail }}</p>
                        <p>Password: {{ signupData.password }}</p>
                        <p>Store in Database?: {{ signupData.storeData }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import SignUp from './SignUp.vue'
    import FullName from './FullName.vue'

    export default {
      data () {
        return {
          signupData: false
        }
      },
      computed: {
        isSubmitted () {
          return this.signupData
        }
      },
      components: {
        signupForm: SignUp,
        fullName: FullName
      }
    }
</script>

<style>
</style>

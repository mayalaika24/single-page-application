<template>
  <div class="text-center">
    <v-dialog persistent v-model="dialog">
      <v-card class="px-md-5 px-2 py-2">
        <div class="title text-center"> Login </div>
        <div class="close-btn"  @click="$emit('close-dialog')">
          <img src="../../assets/closeButton.svg"/>
        </div>
        <v-card-text class="my-5">
          <div class="mb-3">
            <label>Email</label>
            <input v-model="email" type="text" class="form-control">
            <span class="validation" v-if="isSubmitted && !$v.email.required"> Email is required </span>
            <span class="validation" v-if="isSubmitted && !$v.email.email"> Email must be email </span>
          </div>
          <div>
            <label>Password</label>
            <input v-model="password" type="text" class="form-control">
            <span class="validation" v-if="isSubmitted && !$v.password.required"> Password is required </span>
            <span class="validation" v-if="isSubmitted && !$v.password.minLength"> Password must be at least 8 characters </span>
          </div>
        </v-card-text>
        <v-card-actions>
          <v-btn @click="handleSubmit" block>Submit</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>
<script>
import { required, minLength, email } from 'vuelidate/lib/validators'
export default {
  data() {
    return {
      dialog: true,
      email: '',
      password: '',
      isSubmitted: false
    };
  },
  validations: {
    email: { required, email },
    password: { required, minLength:minLength(8) }
  },
  methods: {
    handleSubmit () {
      this.isSubmitted = true
      this.$v.$touch()
        if (this.$v.$invalid) {
          return
        } else {
          this.$emit('close-dialog')
        }
    }
  }
};
</script>
<style>
.v-dialog.v-dialog--active.v-dialog--persistent{
  width: 60%;
}
button.v-btn.v-btn--block.v-btn--is-elevated.v-btn--has-bg.theme--light.v-size--default{
  background: pink;
}
.close-btn{
  position: absolute;
  top: 2%;
  right: 2%;
  font-size: 20px;
  text-shadow: .5px .5px black;
}
.v-dialog__content.v-dialog__content--active{
  font-family: alex;
}
.title.text-center{
  font-family: alex !important;
  font-size: 30px !important;
  font-weight: 700;
  margin-top: 10px;
}
span.v-btn__content{
  font-size: 18px;
  font-weight: 600;
}
.validation{
  color: red;
}
@media (max-width: 550px) {
  .v-dialog.v-dialog--active.v-dialog--persistent{
    width: 90%;
  }
}
</style>

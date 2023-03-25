<template>
  <div id="feedback-section">
    <div class="section-title">Share us your feedback</div>
    <div class="content-container">
      <div class="row row-container justify-content-around">
        <div class="col-8 col-container feedback-container">
          <div class="mb-2">
            <label class="form-label">Name</label>
            <input v-model="name" type="text" class="form-control" />
            <span class="validation" v-if="isSubmitted && !$v.name.required"> Name is required </span>
            <span class="validation" v-if="isSubmitted && !$v.name.minLength"> Name must be at least 3 characters </span>
          </div>
          <div class="mb-2">
            <label class="form-label">Email</label>
            <input v-model="email" type="text" class="form-control" />
            <span class="validation" v-if="isSubmitted && !$v.email.required"> Email is required </span>
            <span class="validation" v-if="isSubmitted && !$v.email.email"> Email must be email </span>
          </div>
          <div class="mb-2">
            <label class="form-label">Feedback</label>
            <textarea v-model="feedback" rows="3" class="form-control"></textarea>
            <span class="validation" v-if="isSubmitted && !$v.feedback.required"> Feedback is required </span>
            <span class="validation" v-if="isSubmitted && !$v.feedback.minLength"> Feedback must be at least 8 characters </span>
          </div>
          <button @click="handleSubmit" class="feedback-btn col-12 my-3">Share</button>
          <FeedbackDialog v-if="dialog" />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { required, minLength, email } from 'vuelidate/lib/validators'
import FeedbackDialog from "./dialogs/FeedbackDialog";
export default {
  components: { FeedbackDialog },
  data () {
    return {
      email: '',
      feedback: '',
      name: '',
      isSubmitted: false,
      dialog: false
    }
  },
  validations: {
    name: { required, minLength: minLength (3) },
    email: { required, email },
    feedback: { required, minLength: minLength (8)}
  },
  methods : {
    handleSubmit () {
      this.isSubmitted = true
      this.$v.$touch()
      if (this.$v.$invalid) {
        return
      } else {
        this.dialog = true
        setTimeout(() => {
          this.dialog = false
        }, 5000)
      }
    }
  }
};
</script>
<style>
#feedback-section {
}
img {
  width: 100%;
  height: 100%;
  border-radius: 8px;
  display: inline-block;
}
.col-4.col-container,
.col-6.col-container {
  height: 100%;
}
.feedback-container {
  border: 2px solid pink;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 20px;
}
label.form-label {
  float: left;
  font-size: 15px;
}
textarea.form-control {
  resize: none;
}
.feedback-btn {
  background: pink;
  outline: none;
  border: none;
  border-radius: 15px;
  height: 30px;
}
</style>

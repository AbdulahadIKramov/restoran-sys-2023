<template>
  <form @click.prevent>
    <div class="row g-3 align-items-center">
      <h1 class="text-center">SingUp form</h1>
      <div class="col-auto d-block mx-auto">
        <input
          type="text"
          class="form-control"
          placeholder="Enter You Name"
          v-model="name"
        />
        <span v-if="v$.name.$error" class="err">
          {{ this.v$.name.$errors[0].$message }}
        </span>
      </div>
    </div>
    <br />
    <div class="row g-3 align-items-center">
      <div class="col-auto d-block mx-auto">
        <input
          type="email"
          class="form-control"
          placeholder="Enter You Email"
          v-model="email"
        />
      </div>
    </div>
    <br />
    <div class="row g-3 align-items-center">
      <div class="col-auto d-block mx-auto">
        <input
          type="password"
          class="form-control"
          placeholder="Enter You Password"
          v-model="pass"
        />
      </div>
    </div>
    <br />
    <div class="row g-3 align-items-center">
      <div class="col-auto d-block mx-auto">
        <button @click="signUpNow" class="btn btn-primary" type="submit">
          Sign Up Now
        </button>
        &nbsp; &nbsp; &nbsp;
        <button
          class="btn btn-link"
          @click="redirectTo({ val: 'Login' })"
          type="submit"
        >
          Login
        </button>
      </div>
    </div>
    <br />
  </form>
</template>

<script>
import { mapActions } from "vuex";
import useValidate from "@vuelidate/core";
import { required } from "@vuelidate/validators";

export default {
  name: "SignUpForm",
  data() {
    return {
      name: "",
      pass: "",
      email: "",
      v$: useValidate(),
    };
  },

  validations() {
    return {
      name: { required },
      pass: { required },
      email: { required },
    };
  },

  methods: {
    ...mapActions(["redirectTo"]),
    // LoginPage() {
    //   this.$router.push({ name: "Login" });
    // },

    signUpNow() {
      this.v$.$validate();
      if (!this.v$.$error) {
        console.log("succes", this.v$);
      } else {
        console.log("errer", this.v$.name.$errors[0].$mssage);
      }
    },
  },
};
</script>

<style></style>

<template>
   <form @click.prevent>
     <div class="row g-3 align-items-center">
      <h1 class="text-center">Login</h1>
       <div class="col-auto d-block mx-auto">
         <input type="email" class="form-control" placeholder="Enter You Email" v-model="email" />
       </div>
     </div>
     <br />
     <div class="row g-3 align-items-center">
       <div class="col-auto d-block mx-auto">
         <input type="password" class="form-control" placeholder="Enter You Password" v-model="pass" />
       </div>
     </div>
     <br />
     <div class="row g-3 align-items-center">
       <div class="col-auto d-block mx-auto">
         <button class="btn btn-primary" type="submit">Login</button> &nbsp; &nbsp; &nbsp;
         <button class="btn btn-link" @click="redirectTo({val: 'SignUp'})" type="submit">Sign Up</button>
       </div>
     </div>
     <br />
   </form>
 </template>
 
 <script>
import { mapActions } from 'vuex';

 export default {
   name: "LoginForm",
   data() {
     return {
       pass: "",
       email: "",
     };
   },
   methods: {
      ...mapActions(['redirectTo'])
      // signUpPage() {
      //    this.$router.push({name: 'SignUp'})
      // }
   }
 };
 </script>
 
 <style></style>
 
<template>
    <v-flex sm8 offset-sm2>
        <v-card>
        <v-toolbar dark>
            <v-toolbar.title>Login</v-toolbar.title>
        </v-toolbar>>
    <v-form>
    <v-container>
      <v-row>
        <v-col
          cols="12"
          md="4"
        >
          <v-text-field
            v-model="userName"
            label="User Name"
            required
          ></v-text-field>
          <v-text-field
            v-model="password"
            label="Password"
            required
          ></v-text-field>
        </v-col>
      </v-row>
    </v-container>
        <v-btn @click="login">Login</v-btn>
  </v-form>
         </v-card>
  </v-flex>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            userName: "",
            password: ""
        };
    },
    methods: {
        async login() {
            
          this.$store.dispatch('login', {userName: this.userName, password: this.password});
            
        }
    }
};
</script>
<template>
  <div class="login">
    <h1>LOG IN HERE</h1>
    <!-- Login Form HTML ... -->
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'LoginView',
  data() {
    return {
      email: '',
      password: '',
    };
  },
  methods: {
    login() {
      const userData = {
        email: this.email,
        password: this.password,
      };

      axios.post('/api/login', userData)
        .then(response => {
          // Handle the successful response from the API
          console.log('Login Successful!', response.data);
          // Redirect the user to the appropriate page (e.g., dashboard)
          // this.$router.push('/dashboard');
        })
        .catch(error => {
          // Handle the error response from the API
          console.error('Login Error:', error.response.data);
        });
    },
  },
};
</script>

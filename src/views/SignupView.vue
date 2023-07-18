<template>
  <div class="Signup">
    <h1>Sign UP HERE</h1>
    <!-- Signup Form HTML ... -->
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'SignupView',
  data() {
    return {
      username: '',
      email: '',
      password: '',
    };
  },
  methods: {
    signup() {
      const userData = {
        username: this.username,
        email: this.email,
        password: this.password,
      };

      axios.post('/api/signup', userData)
        .then(response => {
          // Handle the successful response from the API
          console.log('Sign Up Successful!', response.data);
          // Redirect the user to the appropriate page after sign-up (e.g., dashboard)
          // this.$router.push('/dashboard');
        })
        .catch(error => {
          // Handle the error response from the API
          console.error('Sign Up Error:', error.response.data);
        });
    },
  },
};
</script>

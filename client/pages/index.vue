<template>
  <section class="container">
    <div>
      <h1>Home</h1>
    </div>
  </section>
</template>

<script>
import Logo from "~/components/Logo.vue";

export default {

	mounted() {
    this.isLogin();
  },

  data() {
      return {
          form: {
              email: '',
              password: ''
          },
      }
  },
  components: {
    Logo
  },

  methods: {
    isLogin() {
       if( this.$router.history.current.query ) {
          this.$auth.login({data: this.$router.history.current.query})
          this.$router.push({name: 'index'});
       }
    },
  },
};
</script>

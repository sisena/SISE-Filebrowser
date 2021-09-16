<template>
  <div id="login" />
</template>

<script>
import { login } from "../utils/auth";

export default {
  name: "autologin",
  mounted() {
    this.autologin();
  },
  methods: {
    async autologin() {
      let redirect = this.$route.query.redirect;
      if (redirect === "" || redirect === undefined || redirect === null) {
        redirect = "/files/";
      }
      await login("", "", "");
      this.$router.push({ path: redirect });
    },
  },
};
</script>

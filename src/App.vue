<template>
  <div class="container-layout">
    <HeaderTopBar @callFormLogin="formLogin" />
    <AccessForm
      @closeForm="closeAccessForm"
      @setToFormLogin="setToLogin"
      @setToFormRegister="setToRegister"
      :hiddenAccessForm="hiddeBoxModal"
      :hiddenFormLogin="login"
      :hiddenFormRegister="register"
    />
    <RouterView />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import HeaderTopBar from "@/components/Header/HeaderTopBar/index.vue";
import AccessForm from "@/components/Forms/AccessForm/index.vue";

export default defineComponent({
  name: "App",
  components: { HeaderTopBar, AccessForm },
  data() {
    return {
      hiddeBoxModal: false,
      register: false,
      login: false,
    };
  },

  methods: {
    formLogin() {
      this.hiddeBoxModal = true;
      this.login = true;
    },

    closeAccessForm() {
      this.hiddeBoxModal = false;
    },

    setToRegister() {
      this.login = false;
      this.register = true;
    },

    setToLogin() {
      this.register = false;
      this.login = true;
    },
  },
});
</script>

<style lang="scss">
.container-layout {
  max-width: 1350px;
  margin: 0 auto;
}
</style>

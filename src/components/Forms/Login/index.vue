<template>
  <form @submit.prevent="$emit('handleLogin')">
    <header>
      <h2>Bem vindo(a) de volta ao E-tech</h2>
      <p>Realize seu login e boas compras!</p>
    </header>
    <div class="fields">
      <BaseInput placeholder="E-mail" :icon_name="'email'" />
      <BaseInput
        placeholder="Senha"
        :hiddenRevellingPassword="true"
        :icon_name="'password'"
      />
      <MainButton
        type="submit"
        class="btn-rounded primary"
        :btn_title="'Login'"
        @handleEvent="teste"
      />
      <p>
        Ainda não tem uma conta?
        <span class="key-field" @click="(_$event) => $emit('changeForm')">
          Registrar
        </span>
      </p>
    </div>
  </form>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import MainButton from "@/components/Button/index.vue";
import BaseInput from "@/components/Inputs/BaseInput.vue";

export default defineComponent({
  name: "Login",
  components: { MainButton, BaseInput },
  emits: ["changeForm", "handleLogin"],
  methods: {
    teste() {
      alert("login");
    },
  },
});
</script>

<style lang="scss" scoped>
form {
  margin-top: 40px;
  padding: 0 10px;

  header {
    text-align: center;
    padding: 0 50px;

    h2 {
      font-weight: 500;
      font-size: 30px;
      margin-bottom: 10px;
    }
  }

  .fields {
    margin-top: 40px;

    .key-field {
      &:hover {
        text-decoration: underline;
        color: #009acc;
        cursor: pointer;
      }
    }
  }
}
</style>

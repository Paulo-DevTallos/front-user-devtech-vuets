<template>
  <form>
    <header>
      <h2>Seja muito bem vindo(a) ao E-tech</h2>
      <p>Preencha o formulário para comecarmos</p>
    </header>
    <div class="fields">
      <BaseInput placeholder="E-mail" :icon_name="'email'" />
      <BaseInput
        placeholder="Senha"
        :hiddenRevellingPassword="true"
        :icon_name="'password'"
      />
      <MainButton class="btn-rounded primary" />
      <p>
        Ainda não tem uma conta?
        <RouterLink to="/"> Registrar </RouterLink>
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
  }
}
</style>

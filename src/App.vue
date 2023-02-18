<template>
  <div class="container-layout">
    <!--verificar a renderizacao do cabecalho somente se a rota for diferente das rotas de consultas-->
    <HeaderApp />
    <RouterView />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import HeaderApp from "@/components/Header/index.vue";

export default defineComponent({
  name: "App",
  components: { HeaderApp },
});
</script>

<style lang="scss">
.container-layout {
  max-width: 1350px;
  margin: 0 auto;
}
</style>

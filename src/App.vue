<template>
  <div class="container-layout">
    <RouterView />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "App",
});
</script>

<style lang="scss">
.container-layout {
  max-width: 1350px;
  margin: 0 auto;
  background: red;
}
</style>

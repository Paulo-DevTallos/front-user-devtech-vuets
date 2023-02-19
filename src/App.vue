<template>
  <div class="container-layout">
    <HeaderTopBar @callFormRegister="formRegister" />
    <AccessForm v-if="hiddenFormRegister" @closeForm="closeFormRegister" />
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
      hiddenFormRegister: false,
    };
  },

  methods: {
    formRegister() {
      this.hiddenFormRegister = true;
    },
    closeFormRegister() {
      this.hiddenFormRegister = false;
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

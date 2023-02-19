<template>
  <div class="form-container">
    <Icon icon="mdi:close" @click="(_$event) => $emit('closeForm')" />
    <Login />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { Icon } from "@iconify/vue";
import Login from "@/components/Forms/Login/index.vue";

export default defineComponent({
  name: "AccessForm",
  components: { Icon, Login },
  emits: ["closeForm"],
});
</script>

<style lang="scss" scoped>
.form-container {
  width: 450px;
  height: 100%;
  background: #fff;
  position: fixed;
  top: 0;
  right: 0;
  z-index: 1000;
  padding: 25px;
  box-shadow: -2px 2px 10px rgba(0, 0, 0, 0.24);

  svg {
    position: absolute;
    top: 20px;
    right: 20px;
    font-size: 25px;
  }
}
</style>

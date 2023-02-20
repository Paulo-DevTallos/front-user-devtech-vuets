<template>
  <div class="form-container" v-if="hiddenAccessForm">
    <Icon icon="mdi:close" @click="(_$event) => $emit('closeForm')" />
    <Login
      @changeForm="(_$event) => $emit('setToFormRegister')"
      v-if="hiddenFormLogin"
    />
    <Register
      @changeForm="(_$event) => $emit('setToFormLogin')"
      v-if="hiddenFormRegister"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { Icon } from "@iconify/vue";
import Login from "@/components/Forms/Login/index.vue";
import Register from "@/components/Forms/Register/index.vue";

export default defineComponent({
  name: "AccessForm",
  components: { Icon, Login, Register },
  emits: ["closeForm", "setToFormLogin", "setToFormRegister"],
  props: {
    hiddenAccessForm: {
      type: Boolean,
    },
    hiddenFormLogin: {
      type: Boolean,
    },
    hiddenFormRegister: {
      type: Boolean,
    },
  },
  data() {
    return {};
  },

  methods: {},
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

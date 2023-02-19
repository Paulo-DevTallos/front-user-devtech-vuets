<template>
  <div class="input-container">
    <input
      v-bind="$attrs"
      v-model="inputValue"
      :type="inputType"
      v-if="!hiddenRevellingPassword ? (inputType = 'text') : 'password'"
      @blur="handleValue"
    />
    <RevellingPassword
      @toggle="togglePassword"
      v-if="hiddenRevellingPassword"
      :isPassword="isPasswordVisible"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import RevellingPassword from "@/components/Icons/PasswordRevelling.vue";

export default defineComponent({
  name: "BaseInput",
  components: { RevellingPassword },
  emits: ["handleValue"],
  props: {
    currentValue: {
      type: String,
    },
    hiddenRevellingPassword: {
      type: Boolean,
    },
  },
  data() {
    return {
      inputType: "password",
      inputValue: "",
    };
  },

  computed: {
    isPasswordVisible(): boolean {
      return this.inputType === "text";
    },
  },

  methods: {
    handleValue(newValue: FocusEvent) {
      this.$emit("handleValue", newValue);
    },

    togglePassword(): string {
      return (this.inputType = this.isPasswordVisible ? "password" : "text");
    },
  },
});
</script>

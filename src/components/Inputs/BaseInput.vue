<template>
  <div class="input-container">
    <div class="icon-area">
      <Icon :icon="`carbon:${icon_name}`" />
    </div>
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
import { Icon } from "@iconify/vue";
import RevellingPassword from "@/components/Icons/PasswordRevelling.vue";

export default defineComponent({
  name: "BaseInput",
  components: { RevellingPassword, Icon },
  emits: ["handleValue"],
  props: {
    currentValue: {
      type: String,
    },
    hiddenRevellingPassword: {
      type: Boolean,
    },
    icon_name: {
      type: String,
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

<style lang="scss" scoped>
.input-container {
  height: 45px;
  border: 1px solid #d1d1d1;
  border-radius: 24px;
  display: flex;
  align-items: center;
  margin-bottom: 12px;

  .icon-area {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 12%;
    height: 100%;
    border-top-left-radius: 24px;
    border-bottom-left-radius: 24px;
    background: #d1d1d1;

    > svg {
      font-size: 1.3rem;
    }
  }

  input {
    outline: none;
    border: none;
    width: 80%;
    padding-left: 12px;
    font-size: 1rem;
  }
}
</style>

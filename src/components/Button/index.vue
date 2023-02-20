<template>
  <button @click="(_$event) => $emit('handleEvent')">{{ btn_title }}</button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "MainButton",
  emits: ["handleEvent"],
  props: {
    btn_title: {
      type: String,
      required: true,
    },
  },
});
</script>

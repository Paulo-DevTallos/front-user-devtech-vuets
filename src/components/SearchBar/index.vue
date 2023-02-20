<template>
  <div class="input-style">
    <input type="text" placeholder="Pesquise por um produto" />
    <select name="categories">
      <option value="todas as categorias">todas as categorias</option>
      <option value="Smartphone">Smartphones</option>
      <option value="Notebook">Notebooks</option>
    </select>
    <div class="search-icon">
      <Icon icon="carbon:search" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { Icon } from "@iconify/vue";

export default defineComponent({
  name: "SearchBar",
  components: { Icon },
});
</script>

<style lang="scss" scoped>
.input-style {
  width: 90%;
  height: 45px;
  display: flex;
  border: 2px solid #009acc;
  border-radius: 25px;
  padding-left: 30px;

  select,
  input {
    border: none;
    height: 100%;
    outline: none;
    font-size: 1.2rem;
  }

  select {
    width: 30%;
  }

  input {
    width: 75%;
  }

  .search-icon {
    background: #009acc;
    border: 2px solid #009acc;
    width: 10%;
    border-top-right-radius: 18px;
    border-bottom-right-radius: 18px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
  }

  svg {
    font-size: 27px;
    color: #fff;
  }
}
</style>

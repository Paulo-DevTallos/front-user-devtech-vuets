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

<style lang="scss">
.input-style {
  width: 90%;
  height: 50px;
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
    width: 60%;
  }

  .search-icon {
    background: #009acc;
    width: 10%;
    border-top-right-radius: 20px;
    border-bottom-right-radius: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
  }

  svg {
    font-size: 30px;
    color: #fff;
  }
}
</style>

<template>
  <div class="header-actions">
    <div>
      <span>(Nome do usuário) bem vindo(a) ao E-tech Marketplace</span>
    </div>
    <nav class="nav-actions">
      <ul>
        <li>
          <RouterLink to="#">
            <Icon icon="carbon:location" />
            <span>Localize uma loja</span>
          </RouterLink>
        </li>
        <li>
          <RouterLink to="#">
            <Icon icon="carbon:delivery-truck" />
            <span>Encontre seu pedido</span>
          </RouterLink>
        </li>
        <li>
          <Icon icon="carbon:user" />
          <span @click="(_$event) => $emit('callFormRegister')"
            >Registre-se</span
          >
          &nbsp;ou&nbsp;
          <span @click="login">Faca seu login</span>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { Icon } from "@iconify/vue";

export default defineComponent({
  name: "HeaderTopBar",
  components: { Icon },
  emits: ["callFormRegister"],
  data() {
    return {};
  },

  methods: {
    login() {
      alert("chamará o form de login");
    },
  },
});
</script>

<style lang="scss" scoped>
.header-actions {
  padding: 5px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #d1d1d1;

  .nav-actions {
    ul {
      display: flex;

      li {
        border-right: 1px solid #d1d1d1;

        &:last-child {
          border: none;
          padding-right: 0;
          padding: 5px 20px;
          cursor: pointer;
        }

        a {
          padding: 5px 20px;
          display: flex;
          align-items: center;
          color: #333;

          svg {
            margin-right: 7px;
            font-size: 18px;
          }

          span {
            color: #333;
          }
        }
      }
    }
  }
}
</style>

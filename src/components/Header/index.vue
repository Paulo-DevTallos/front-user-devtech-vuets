<template>
  <header class="header">
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
            <span @click="register">Registre-se</span>
            &nbsp;ou&nbsp;
            <span @click="login">Faca seu login</span>
          </li>
        </ul>
      </nav>
    </div>
    <div class="header-application">
      <div class="logo">
        <img :src="logo" alt="logo E-tech" />
      </div>
      <div class="search-bar">
        <Icon icon="mdi:menu" />
        <SearchBar />
      </div>
      <div class="profile-actions">
        <Icon icon="carbon:favorite" />
        <div class="cart">
          <Icon icon="mdi:cart-outline" />
          <span class="cart-notification">0</span>
          <!--essa notificacao só vai aparecer com o usuario logado-->
          <span class="sum-cartvalue">R$ 0,00</span>
          <!--esse valor só vai aparecer com o usuario logado-->
        </div>
      </div>
    </div>
  </header>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { Icon } from "@iconify/vue";
import SearchBar from "@/components/SearchBar/index.vue";

import logo from "@/assets/img/logo-dev-tech-nobg.png";

export default defineComponent({
  name: "HeaderApp",
  components: { Icon, SearchBar },
  data() {
    return {
      logo: logo,
    };
  },

  methods: {
    register() {
      alert("chamará o form de cadastro");
    },
    login() {
      alert("chamará o form de login");
    },
  },
});
</script>

<style lang="scss" scoped>
.header {
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

  .header-application {
    padding: 30px 0;
    display: flex;
    justify-content: space-between;
    align-items: center;

    .logo {
      img {
        width: 200px;
      }
    }

    .search-bar {
      display: flex;
      align-items: center;
      width: 65%;

      svg {
        width: 10%;
        font-size: 40px;
        cursor: pointer;
      }
    }

    .profile-actions {
      font-size: 30px;
      display: flex;
      align-items: center;

      > svg {
        font-size: 30px;
        margin-right: 30px;
      }

      .cart {
        position: relative;
        .cart-notification {
          position: absolute;
          bottom: 0;
          left: 10%;
          background: red;
          color: #fff;
          font-size: 0.8rem;
          display: flex;
          justify-content: center;
          align-items: center;
          width: 20px;
          height: 20px;
          border-radius: 100%;
        }

        svg {
          font-size: 27px;
        }
      }

      .sum-cartvalue {
        margin-left: 10px;
        font-size: 1.3rem;
        font-weight: 500;
      }
    }
  }
}
</style>

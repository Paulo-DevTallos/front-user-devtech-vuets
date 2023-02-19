<template>
  <header class="header">
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
});
</script>

<style lang="scss" scoped>
.header {
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
        cursor: pointer;
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
          cursor: pointer;
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

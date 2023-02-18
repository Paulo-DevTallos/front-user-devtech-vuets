<template>
  <main>
    <section class="home-banner">
      <aside class="menu-categories">
        <header class="header-stylus spacing-list">Menu de categorias</header>
        <ul>
          <li>Smartphones</li>
          <li>Smartwitches</li>
          <li>Tablets</li>
          <li>Notebooks</li>
          <li>Gabinetes</li>
        </ul>
      </aside>
      <div class="into-banner">
        <div class="title-info content-spacing">
          <h1>The new stardard</h1>
          <p>The best of Iphone 14 pro MAX</p>
          <div class="price-banner">
            <span>FROM</span>
            <h3 class="price">R$ <span>8.099,99</span></h3>
            <button>Comprar</button>
          </div>
        </div>
        <div class="image-product content-spacing">
          <img :src="iphone" alt="" />
        </div>
      </div>
    </section>
    <div>Mais pesquisados</div>
    <section>criar secao com lista de algumas renderizacoes</section>
    <section>criar secao com os mais vendidos</section>
    <section>banner de promocao</section>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";

import imageIphone from "@/assets/img/iphone-14pro-max.png";

export default defineComponent({
  name: "HomeView",
  data() {
    return {
      iphone: imageIphone,
    };
  },
});
</script>

<style lang="scss" scoped>
main {
  .home-banner {
    display: flex;

    .menu-categories {
      width: 25%;
      height: 500px;

      .header-stylus {
        background: #009acc;
        border-top-left-radius: 12px;
        color: #fff;
        font-size: 1.2rem;
      }

      .spacing-list {
        padding: 20px;
      }

      ul {
        li {
          @extend .spacing-list;
          border-bottom: 1px solid #d1d1d1;
        }
      }
    }

    .into-banner {
      display: flex;
      width: 75%;
      padding: 20px 0;
      background-image: linear-gradient(#b4b4b4, #fafafa);

      .title-info {
        display: flex;
        flex-direction: column;
        justify-content: center;
        padding-left: 20px;

        h1 {
          font-size: 80px;
          font-weight: 300;
          line-height: 1;
          text-transform: uppercase;
        }

        p {
          font-weight: 500;
          font-size: 1.5rem;
          margin-top: 10px;
        }

        .price-banner {
          margin-top: 20px;

          .price {
            font-size: 25px;

            > span {
              font-size: 60px;
            }
          }

          button {
            width: 200px;
            padding: 15px 0;
            margin-top: 20px;
            border-radius: 12px;
            font-size: 20px;
            background: #009acc;
            border: none;
            color: #fff;
          }
        }
      }

      .image-product {
        img {
          width: 400px;
          filter: drop-shadow(-2px 2px 5px rgba(0, 0, 0, 0.24));
        }
      }
      .content-spacing {
        width: 50%;
      }
    }
  }
}
</style>

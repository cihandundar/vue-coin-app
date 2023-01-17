<template>
  <section class="container">
    <div class="container__btn">
      <button @click="isOpen = true" style="margin-inline: 20px">
        Add Stock
      </button>
      <button @click="reloadPage">Refresh</button>
    </div>
    <div class="right"></div>
    <div class="center"></div>
    <div class="wrapper" v-if="isOpen">
      <div class="row">
        <div class="wrapper__item">
          <coin-item></coin-item>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import CoinItem from "@/components/CoinItem.vue";

export default {
  name: `Popup`,
  props: ["coinitem"],
  components: {
    CoinItem,
  },
  setup() {
    return {
      CoinItem,
    };
  },
  data() {
    return {
      isOpen: false,
    };
  },
  methods: {
    reloadPage() {
      window.location.reload();
    },
  },
};
</script>

<style lang="scss" scoped>
.wrapper {
  position: relative;
}

.center {
  position: fixed;
  right: 50%;
  height: 100vh;
  border-right: 1px solid #000;
  margin-top: 15px;
}

.right {
  width: 550px;
  height: 550px;
  background-color: rgb(190, 184, 184);
  border-radius: 50%;
  position: fixed;
  top: 20%;
  right: 10%;
}

.row {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  align-content: center;
}

button {
  background-color: #0f6fe8;
  color: #fff;
  border: none;
  width: 130px;
  height: 45px;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 600;
  letter-spacing: 1px;
}
</style>

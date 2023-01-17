<template>
  <main class="main">
    <div class="main__container">
      <div v-if="page === `coinitem`"><Popup /></div>
      <div>
        <button v-on:click="navigateTo(`coinlist`)" class="view">
          View List
        </button>
        <button v-on:click="navigateTo(`coinitem`)" class="view back">
          Back
        </button>
      </div>
      <div v-if="page === `coinlist`">
        <coin-list></coin-list>
      </div>
    </div>
  </main>
</template>

<script>
import CoinList from "./components/CoinList.vue";
import Popup from "./components/Popup.vue";

export default {
  name: "App",
  data() {
    return {
      page: "coinitem",
    };
  },
  components: {
    Popup,
    CoinList,
  },

  methods: {
    navigateTo(page) {
      this.page = page;
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;700;900&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Roboto", sans-serif;
}

.main {
  max-width: 1200px;
  margin: 0 auto;
  border-bottom: 1px solid #000;
  padding-block: 15px;
  &__container {
    display: flex;
    justify-content: space-between;
  }
}

.view {
  color: #fff;
  border: none;
  width: 130px;
  height: 45px;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 600;
  letter-spacing: 1px;
  background: #000;
  color: #f9f9f9;
}
.back {
  margin-left: 10px;
}
ul {
  > li {
    list-style-type: none;
  }
}
</style>

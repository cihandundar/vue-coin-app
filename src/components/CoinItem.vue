<template>
  <section class="section">
    <div class="section__container">
      <ul>
        <div class="input">
          <input type="text" v-model="search" placeholder="Search..." />
        </div>
        <li v-for="item in filteredList" :key="item.id">
          {{ item.symbol }}
          <div class="btn">
            <update-button @add="addToCart(item.id)"></update-button>
            <remove-button @remove="removeItem(item)"></remove-button>
          </div>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
import axios from "axios";
import UpdateButton from "./UpdateButton.vue";
import RemoveButton from "./RemoveButton.vue";

export default {
  name: `CoinItem`,
  components: {
    UpdateButton,
    RemoveButton,
  },

  data() {
    return {
      items: [],
      search: ``,
      quantity: 1,
    };
  },

  created: function () {
    axios
      .get(`https://api2.binance.com/api/v3/ticker/24hr`)
      .then((response) => {
        this.items = response.data;
      });
  },
  computed: {
    filteredList() {
      return this?.items?.filter((item) => {
        return item?.symbol
          ?.toLowerCase()
          ?.includes(this?.search?.toLowerCase());
      });
    },
  },

  methods: {
    addToCart(item) {
      this.items.push(item.id);
      console.log(this.items);
    },

    removeItem(item) {
      this?.items?.splice(item, 1);
    },
  },
};
</script>

<style lang="scss" scoped>
.section {
  &__container {
    min-width: 580px;
    position: relative;
    left: 50%;
  }
}

.input {
  width: 100%;
  padding-block: 10px;

  > input {
    width: 100%;
    height: 35px;
    border-radius: 6px;
    border: 1px solid #000;
    padding-left: 10px;
    &:focus {
      outline: none;
    }
  }
}

ul {
  margin-top: 20px;
  border-radius: 8px;
  padding: 20px;
  background-color: #fff;
  -webkit-box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.75);
  box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.75);
  > li {
    font-size: 12px;
    margin-top: 10px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-weight: bold;
  }
}

.btn {
  display: flex;
  align-items: center;
}
</style>

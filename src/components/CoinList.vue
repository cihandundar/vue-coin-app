<template>
  <div class="list">
    <div class="list__container">
      <ul>
        <li v-for="item in filteredList" :key="item.id">
          {{ item.symbol }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: `CoinList`,
};
</script>

<style lang="scss" scoped>
// .list {
//   border-radius: 8px;
//   padding: 20px;
//   background-color: #fff;
//   -webkit-box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.75);
//   -moz-box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.75);
//   box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.75);
//   position: fixed;
//   left: 12%;
//   top: 20%;
//   &__container {
//     span {
//       color: #000;
//     }
//   }
// }
</style>

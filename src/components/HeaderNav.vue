<template>
  <header class="header">
    <popup />
    <!-- <div v-if="arrlastPrice?.length > 0">
      <pie-chart
        :chartData="arrlastPrice"
        :options="chartOptions"
        label="lastPrice"
      ></pie-chart>
    </div> -->
  </header>
</template>

<script>
import Popup from "./Popup.vue";
// import axios from "axios";
// import moment from "moment";
// import PieChart from "./PieChart.vue";

export default {
  name: `Header`,
  components: {
    Popup,
    // PieChart,
  },
  //   data() {
  //     return {
  //       arrlastPrice: [],
  //       positiveChartColors: {
  //         borderColor: "#077187",
  //         pointBorderColor: "#0E1428",
  //         pointBackgroundColor: "#AFD6AC",
  //         backgroundColor: "#74A57F",
  //       },
  //       chartOptions: {
  //         responsive: true,
  //         maintainAspectRatio: false,
  //       },
  //     };
  //   },
  //   async created() {
  //     const { data } = await axios.get(
  //       `https://api2.binance.com/api/v3/ticker/24hr`
  //     );
  //     data.forEach((d) => {
  //       const date = moment(d?.date, "YYYYMMDD").format("MM/DD");
  //       const { lastPrice } = d;
  //       this?.arrlastPrice?.push({ date, total: lastPrice });
  //       console.log(this.arrlastPrice);
  //     });
  //   },
};
</script>

<style lang="scss" scoped></style>

<!-- <template>
  <div></div>
</template>

<script>
import { Pie } from "vue-chartjs";

export default {
  extends: Pie,
  name: `PieChart`,
  props: {
    label: {
      type: String,
    },
    chartData: {
      type: Array,
    },
    options: {
      type: Object,
    },
  },

  mounted() {
    const dates = this?.chartData?.map((d) => d.date).reverse();
    const totals = this?.chartData?.map((d) => d.total).reverse();

    this.renderChart(
      {
        labels: dates,
        datasets: [
          {
            label: this.label,
            data: totals,
          },
        ],
      },
      this.options
    );
  },
};
</script>

<style lang="scss" scoped></style> -->

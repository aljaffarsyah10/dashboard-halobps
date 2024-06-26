<template>
  <!-- <div class="chart-renderer" style="height: 400px" v-if="resultSet"> -->
  <div class="chart-renderer" style="" v-if="resultSet">
    <component
      v-if="componentType"
      :is="componentType"
      :data="data(resultSet)"
      :stacked="isStacked"
      height="100%"
      width="100%"
    ></component>

    <Table v-if="chartType === 'table'" :result-set="resultSet"></Table>

    <div
      v-if="chartType === 'number'"
      class="number-container"
      style="
        display: flex;
        justify-content: center;
        height: 100%;
        flex-direction: column;
      "
    >
      <div
        v-for="item in resultSet.series()"
        :key="item.key"
        style="font-size: 24px"
      >
        {{ item.series[0].value }}
      </div>
    </div>
  </div>
</template>

<script>
import { ref, watch } from "vue";
import { QueryRenderer } from "@cubejs-client/vue3";
import Table from "./TableCube.vue";

export default {
  name: "ChartRenderer",

  props: {
    cubejsApi: Object,
    query: Object,
    chartType: String,
  },
  setup(props) {
    const resultSet = ref(null);

    watch(
      () => props.query,
      async () => {
        const result = await props.cubejsApi.load(props.query);
        resultSet.value = result;
      },
      { immediate: true }
    );

    return {
      resultSet,
    };
  },
  computed: {
    componentType() {
      if (this.chartType === "table" || this.chartType === "number") {
        return null;
      }

      return [
        this.chartType === "bar" ? "column" : this.chartType,
        "-chart",
      ].join("");
    },

    isStacked() {
      return this.chartType === "area";
    },
  },
  methods: {
    data(resultSet) {
      if (["line", "area"].includes(this.chartType)) {
        return this.series(resultSet);
      }

      if (this.chartType === "pie") {
        return this.pairs(resultSet);
      }

      if (this.chartType === "bar") {
        return this.seriesPairs(resultSet);
      }
    },

    series(resultSet) {
      if (!resultSet) {
        return [];
      }

      const seriesNames = resultSet.seriesNames();
      const pivot = resultSet.chartPivot();
      const series = [];
      seriesNames.forEach((e) => {
        const data = pivot.map((p) => [p.x, p[e.key]]);
        series.push({
          name: e.title,
          data,
        });
      });
      return series;
    },

    pairs(resultSet) {
      return resultSet.series()[0].series.map((item) => [item.x, item.value]);
    },

    seriesPairs(resultSet) {
      return resultSet.series().map((seriesItem) => ({
        name: seriesItem.title,
        data: seriesItem.series.map((item) => [item.x, item.value]),
      }));
    },
  },
  components: {
    QueryRenderer,
    Table,
  },
};
</script>

<style>
/* your styles here */
</style>

<template>
  <Bar id="my-chart-id" :options="chartOptions" :data="chartData" />
</template>

<script>
import { Bar } from "vue-chartjs";
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale,
} from "chart.js";

ChartJS.register(
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale
);

export default {
  name: "BarChart",
  components: { Bar },
  data() {
    return {
      chartData: {
        labels: [
          "Jan",
          "Feb",
          "Mar",
          "Apr",
          "May",
          "June",
          "July",
          "Aug",
          "Sept",
        ],
        datasets: [
          {
            data: [40, 20, 12, 40, 20, 12, 40, 20, 12],
            label: "Data One",
            backgroundColor: "rgb(23 76 254)",
            barThickness: "15",
            borderRadius: 500,
            borderSkipped: false,
          },
          {
            data: [80, 80, 80, 80, 80, 80, 80, 80, 80],
            label: "Data One",
            backgroundColor: "#d9d9d9",
            barThickness: "15",
            borderRadius: 50,
            borderSkipped: false,
          },
        ],
      },
      chartOptions: {
        plugins: {
            tooltip:{
                enabled:false
            },
          legend: {
            display: false,
          },
        },
        responsive: true,
        maintainAspectRatio: true,
        scales: {
          x: {
            stacked: true,
            grid: {
              display: false,
            },
          },
          y: {
            stacked: true,
            min: 0,
            max: 80,
            grid: {
              display: false,
            },
             ticks: {
                // forces step size to be 50 units
                stepSize: 20
            }
          },
        },
      },
    };
  },
};
</script>
<style scoped>
canvas {
  max-height: 200px !important;
}
</style>
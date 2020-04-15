<template>
  <div class="chart">

    <h2 class="main-header">Data Visualizations </h2> <h3>(Notes: Still in Development 👨‍💻)</h3>
    <canvas class="planet-chart">

    </canvas>
  </div>
</template>

<script>
import Chart from 'chart.js';
// import planetChartData from './chart-data';

const planetChartData = {
  type: 'bar',
  data: {
    labels: [
      '1',
      '2',
      '3',
      '4',
      '5',
      '6',
      '7',
      '8',
      '9',
      '10',
    ],
    datasets: [
      {
        // one line graph
        label: 'Estimated Impact',
        data: [10, 10, 11, 22, 34, 41, 27, 14, 15, 18],
        backgroundColor: [
          'wheat', // Blue
          'wheat',
          'wheat',
          'wheat',
          'wheat',
          'wheat',
          'wheat',
          'wheat',
          'wheat',
          'wheat',
        ],
        borderColor: [
          '#36495d',
          '#36495d',
          '#36495d',
          '#36495d',
          '#36495d',
          '#36495d',
          '#36495d',
          '#36495d',
          '#36495d',
          '#36495d',
        ],
        borderWidth: 1,
      },
      {
        // another line graph
        label: 'Estimated Severe Impact (Worst Case Scenario)',
        data: [4.8, 12.1, 12.7, 6.7, 50, 70, 50.7, 49.2, 54, 63],
        backgroundColor: [
          '#6649b8', // Green
          '#6649b8',
          '#6649b8',
          '#6649b8',
          '#6649b8',
          '#6649b8',
          '#6649b8',
          '#6649b8',
          '#6649b8',
          '#6649b8',
        ],
        borderColor: ['#6649b8'],
        borderWidth: 3,
      },
    ],
  },
  options: {
    responsive: true,
    lineTension: 1,
    scales: {
      yAxes: [
        {
          ticks: {
            beginAtZero: true,
            padding: 25,
          },
        },
      ],
    },
  },
};

export default {
  name: 'DataChart',
  data() {
    return {
      planetChartData,
    };
  },
  methods: {
    createChart(chartId, chartData) {
      const ctx = document.querySelector('.planet-chart');
      // alert('Hello world');
      // eslint-disable-next-line
      const myChart = new Chart(ctx, {
        type: chartData.type,
        data: chartData.data,
        options: chartData.options,
      });
    },
  },
  mounted() {
    this.createChart('planet-chart', this.planetChartData);
  },
};
</script>

<style>
  .chart {
    /* width: 400px;
    margin: 1rem 2rem; */
    margin-top: 1.5rem;
  }
</style>

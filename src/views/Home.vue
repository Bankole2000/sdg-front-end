<template>
  <div class="home">
  <Title title="Covid-19 Impact Estimator"/>
  <main>
    <form @submit.prevent="clicked">
  <div class="form-field">
    <input type="number" name="population" id="population" data-population autocomplete="off"
    v-model="population" required>
    <label for="population" class="label-name">
      <span class="input-content-name">Population</span>
    </label>
  </div>
  <div class="form-field">
  <input type="number" name="timeToElapse" id="timeToElapse"
  data-time-to-elapse required autocomplete="off"
  v-model="timeToElapse">
    <label for="timeToElapse" class="label-name">
      <span class="input-content-name">Time to Elapse</span>
    </label>
  </div>
  <div class="form-field">
    <input type="number" name="reportedCases" id="reportedCases"
    data-reported-cases required autocomplete="off"
    v-model="reportedCases">
    <label for="reportedCases" class="label-name">
      <span class="input-content-name">Reported Cases</span>
    </label>
  </div>
  <div class="form-field">
    <input type="number" name="totalHospitalBeds" id="totalHospitalBeds"
    data-total-hospital-beds required autocomplete="off"
    v-model="totalHospitalBeds">
    <label for="totalHospitalBeds" class="label-name">
      <span class="input-content-name">Total Hospital Beds</span>
    </label>
  </div>
  <label for="selectPeriodType" class="select-label">Select Period Type:</label>
  <select name="periodType" id="selectPeriodType" data-period-type v-model="periodType">
    <option value="days">days</option>
    <option value="weeks">weeks</option>
    <option value="months">months</option>
  </select>
  <button type="submit" class="btn btn-default" data-go-estimate>Get Impact Data</button>
    </form>
    <div class="divider"></div>
    <div class="container">
      <div class="row">

      <div class="column">
        <h3 class="main-header">Regional Data</h3>
        <p><strong>Name</strong>: {{region.name}}</p>
        <p><strong>Average Age</strong>: {{region.avgAge}}</p>
        <p><strong>Avg Daily Income</strong>: ${{region.avgDailyIncomeInUSD}}</p>
        <p><strong>Avg Income Population</strong>:
        {{region.avgDailyIncomePopulation}} %</p>
      </div>
      <div class="column">
        <h3 class="main-header">Input Data</h3>
        <p><strong>Population</strong>: {{population}}</p>
        <p><strong>Time To Elapse</strong>: {{timeToElapse}}</p>
        <p><strong>Reported Cases</strong>: {{reportedCases}}</p>
        <p><strong>No of Hospital Beds</strong>: {{totalHospitalBeds}}</p>
        <p><strong>Time Period Type</strong>: {{periodType}}</p>
      </div>
    </div>
    </div>
  </main>
  </div>
</template>

<script>
// @ is an alias to /src
import Title from '@/components/Title.vue';

export default {
  name: 'Home',
  data() {
    return {
      population: '',
      timeToElapse: '',
      reportedCases: '',
      totalHospitalBeds: '',
      periodType: 'days',
      region: {
        name: 'Africa',
        avgAge: 19.7,
        avgDailyIncomeInUSD: 3.1,
        avgDailyIncomePopulation: 73,
      },
    };
  },
  components: {
    Title,
  },
  methods: {
    clicked() {
      alert('You clicked');
    },
  },
};
</script>

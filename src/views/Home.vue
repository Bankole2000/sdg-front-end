<template>
  <div class="home">
  <Title title="Covid-19 Impact Estimator"/>
  <main>
    <form @submit.prevent="clicked">
  <div class="form-field">
    <input type="number" name="population" id="population" data-population autocomplete="off"
    v-model="data.population" required>
    <label for="population" class="label-name">
      <span class="input-content-name">Population</span>
    </label>
  </div>
  <div class="form-field">
  <input type="number" name="timeToElapse" id="timeToElapse"
  data-time-to-elapse required autocomplete="off"
  v-model="data.timeToElapse">
    <label for="timeToElapse" class="label-name">
      <span class="input-content-name">Time to Elapse</span>
    </label>
  </div>
  <div class="form-field">
    <input type="number" name="reportedCases" id="reportedCases"
    data-reported-cases required autocomplete="off"
    v-model="data.reportedCases">
    <label for="reportedCases" class="label-name">
      <span class="input-content-name">Reported Cases</span>
    </label>
  </div>
  <div class="form-field">
    <input type="number" name="totalHospitalBeds" id="totalHospitalBeds"
    data-total-hospital-beds required autocomplete="off"
    v-model="data.totalHospitalBeds">
    <label for="totalHospitalBeds" class="label-name">
      <span class="input-content-name">Total Hospital Beds</span>
    </label>
  </div>
  <label for="selectPeriodType" class="select-label">Select Period Type:</label>
  <select name="periodType" id="selectPeriodType" data-period-type v-model="data.periodType">
    <option value="days">days</option>
    <option value="weeks">weeks</option>
    <option value="months">months</option>
  </select>
  <button type="submit" class="btn btn-default" data-go-estimate>Get Impact Data</button>
    </form>
    <Loader v-if="loading" />
    <div class="container" v-if="!loading">
      <div class="divider"></div>
      <div class="row">

      <div class="column">
        <h2 class="main-header" style="display: flex;">Regional Data
          <img @click.prevent='toggleRegionEdit' src="../assets/styles/assets/svgs/edit.svg"
          class="header-icon" :class="{'editing-icon': editing}" alt="edit icon"
          style="width: 2rem; margin: auto;
          cursor: pointer;" title="Edit Region Data"></h2>
        <h4><strong class="field-title">Name</strong>:
        <span v-if="!editing">{{data.region.name}}</span>
        <input type="text" v-model="data.region.name" v-if="editing"> </h4>
        <h4><strong class="field-title">Average Age</strong>:
        <span v-if="!editing">{{data.region.avgAge}}</span>
        <input type="number" v-model="data.region.avgAge" v-if="editing"></h4>
        <h4><strong class="field-title">Avg Daily Income</strong>:
        $<span v-if="!editing">{{data.region.avgDailyIncomeInUSD}}</span>
        <input type="text" maxlength="5" size="5" v-model="data.region.avgDailyIncomeInUSD"
        v-if="editing"></h4>
        <h4><strong class="field-title">Avg Income Population</strong>:
        <span v-if="!editing">{{data.region.avgDailyIncomePopulation}} %</span>
        <input type="text" maxlength="2" size="3"
        v-model="data.region.avgDailyIncomePopulation"
        v-if="editing"></h4>
      </div>
      <div class="column">
        <h2 class="main-header">Input Data</h2>
        <h4><strong class="field-title">Population</strong>:
        {{data.population}}</h4>
        <h4><strong class="field-title">Time To Elapse</strong>:
        {{data.timeToElapse}} {{data.timeToElapse == 1 ? data.periodType.slice(0, -1)
        : data.periodType}}</h4>
        <h4><strong class="field-title">Reported Cases</strong>:
        {{data.reportedCases}}</h4>
        <h4><strong class="field-title">No of Hospital Beds</strong>:
        {{data.totalHospitalBeds}}</h4>
      </div>
    </div>
    <div class="divider"></div>
    <div class="row" v-if="showEstimate">

      <div class="column">
        <h2 class="main-header">Impact</h2>
        <h4><strong class="field-title">Currently Infected</strong>:
        {{estimate.impact.currentlyInfected}}</h4>
        <h4><strong class="field-title">infections by {{time}}</strong>:
        {{estimate.impact.infectionsByRequestedTime}}</h4>
        <h4><strong class="field-title">Severe Cases by {{time}}</strong>:
        {{estimate.impact.severeCasesByRequestedTime}}</h4>
        <h4><strong class="field-title">Cases for ICU</strong>:
        {{estimate.impact.casesForICUByRequestedTime}}</h4>
        <h4><strong class="field-title">Cases for Ventilators</strong>:
        {{estimate.impact.casesForVentilatorsByRequestedTime}}</h4>
        <h4><strong class="field-title">Economic Costs</strong>:
        $ {{estimate.impact.dollarsInFlight}}</h4>

      </div>
      <div class="column">
        <h2 class="main-header">Severe Impact</h2>
        <h4><strong class="field-title">Currently Infected</strong>:
        {{estimate.severeImpact.currentlyInfected}}</h4>
        <h4><strong class="field-title">infections by {{time}}</strong>:
        {{estimate.severeImpact.infectionsByRequestedTime}}</h4>
        <h4><strong class="field-title">Severe Cases by {{time}}</strong>:
        {{estimate.severeImpact.severeCasesByRequestedTime}}</h4>
        <h4><strong class="field-title">Cases for ICU</strong>:
        {{estimate.severeImpact.casesForICUByRequestedTime}}</h4>
        <h4><strong class="field-title">Cases for Ventilators</strong>:
        {{estimate.severeImpact.casesForVentilatorsByRequestedTime}}</h4>
        <h4><strong class="field-title">Economic Costs</strong>:
        $ {{estimate.severeImpact.dollarsInFlight}}</h4>
      </div>
    </div>
    </div>

  </main>
  </div>
</template>

<script>
// @ is an alias to /src
import Title from '@/components/Title.vue';
import Loader from '@/components/Loader.vue';
import axios from 'axios';

export default {
  name: 'Home',
  data() {
    return {
      data: {
        population: '',
        timeToElapse: ' ',
        reportedCases: '',
        totalHospitalBeds: '',
        periodType: 'days',
        region: {
          name: 'Africa',
          avgAge: 19.7,
          avgDailyIncomeInUSD: 3.1,
          avgDailyIncomePopulation: 73,
        },
      },
      estimate: {},
      showEstimate: false,
      loading: false,
      editing: false,
    };
  },
  components: {
    Title,
    Loader,
  },
  methods: {
    clicked() {
      this.loading = true;
      this.data.avgDailyIncomePopulation /= 100;
      const data = { ...this.data };
      axios.post('https://sdg-backend.herokuapp.com/api/v1/on-covid-19', data)
        .then((res) => {
          console.log(res);
          this.estimate = res.data;
          this.showEstimate = true;
          this.loading = false;
          this.time = this.data.timeToElapse === 1 ? `${this.data.timeToElapse} ${this.data.periodType}`
            : `${this.data.timeToElapse} ${this.data.periodType.slice(0, -1)}`;
        })
        .catch((err) => console.log(err));
    },
    toggleRegionEdit() {
      this.editing = !this.editing;
    },
  },
};
</script>

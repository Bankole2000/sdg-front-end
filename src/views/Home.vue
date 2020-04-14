<template>
  <div class="home">
  <Title title="Covid-19 Impact Estimator"/>
  <main>

  <div class="form-field">
    <input type="text" name="population" data-population autocomplete="off"
    v-model="population" required>
    <label for="population" class="label-name">
      <span class="input-content-name">Population</span>
    </label>
  </div>
  <div class="form-field">
  <input type="text" name="timeToElapse" data-time-to-elapse required autocomplete="off"
  v-model="timeToElapse">
    <label for="timeToElapse" class="label-name">
      <span class="input-content-name">Requested Projection Time</span>
    </label>
  </div>
  <div class="form-field">
    <input type="text" name="reportedCases" data-reported-cases required autocomplete="off"
    v-model="reportedCases">
    <label for="reportedCases" class="label-name">
      <span class="input-content-name">Reported Cases</span>
    </label>
  </div>
  <div class="form-field">
    <input type="text" name="totalHospitalBeds"
    data-total-hospital-beds required autocomplete="off"
    v-model="totalHospitalBeds">
    <label for="totalHospitalBeds" class="label-name">
      <span class="input-content-name">Total Hospital Beds</span>
    </label>
  </div>

  <select name="periodType" id="">
    <option value="days">days</option>
    <option value="weeks">weeks</option>
    <option value="months">months</option>
  </select>
  <button type="submit" class="btn btn-default" data-go-estimate>Get Impact Data</button>

    <Index msg="Welcome to Your Vue.js App"/>

  </main>
  </div>
</template>

<script>
// @ is an alias to /src
import Title from '@/components/Title.vue';
import Index from '@/components/Index.vue';

export default {
  name: 'Home',
  data() {
    return {
      population: '',
      timeToElapse: '',
      reportedCases: '',
      totalHospitalBeds: '',
      periodType: '',
    };
  },
  components: {
    Title,
    Index,
  },
};
</script>

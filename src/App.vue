<template>
  <div
    id="app"
    class="font-sans text-black min-h-screen bg-grey-darker p-5"
    style="padding-top: 14rem; padding-bottom: 14rem"
  >
    <div class="mw-100 mh-100 bg-white rounded shadow-lg p-8">
      <div class="w-100 p-3 bg-secondary text-light">
        <label class="form-label">DCDS TimeCard</label>
        <search-select v-model="option" class="mb-2"></search-select>
        <br />
        <p>Trying to return selected name: '{{option}}'</p>
        <label class="form-label mb-2">Select Friday in Week Of:</label>
        <date-select v-model="date" class="mb-2"></date-select>
        <br />
        <p>Trying to return selected date: '{{date}}'</p>
        <div class="text-left">
          <div>
            <label class="form-label text-left mb-2">Project Work:</label>
            <vue-numeric-input
              id="project"
              v-model="value1"
              :min="1"
              :max="100"
              :step="1"
            ></vue-numeric-input>
          </div>
          <div>
            <label class="form-label mb-2">Support Work:</label>
            <vue-numeric-input
              id="support"
              v-model="value2"
              :min="1"
              :max="100"
              :step="1"
            ></vue-numeric-input>
          </div>
          <div>
            <label class="form-label mb-2">Meetings/CVR:</label>
            <vue-numeric-input
              id="meeting"
              v-model="value3"
              :min="1"
              :max="100"
              :step="1"
            ></vue-numeric-input>
          </div>
          <div>
            <label class="form-label mb-2">Travel to/from Post:</label>
            <vue-numeric-input
              id="travel"
              v-model="value4"
              :min="1"
              :max="100"
              :step="1"
            ></vue-numeric-input>
          </div>
          <div>
            <label class="form-label mb-2"
              >Army Requirements (350-1, STT, ect):</label
            >
            <vue-numeric-input
              id="req"
              v-model="value5"
              :min="1"
              :max="100"
              :step="1"
            ></vue-numeric-input>
          </div>
          <br />
          <p>Total Hours: '{{ value1 + value2 + value3 + value4 + value5 }}'</p>
        </div>
        <div class="text-right">
          <button type="button" class="btn btn-blue">Next</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SearchSelect from "./components/SoldierSelect.vue";
import DateSelect from "./components/DateSelect.vue";
// import Vue from 'Vue';
import VueNumericInput from "vue-numeric-input";

// import Datepicker from "vuejs-datepicker/dist/vuejs-datepicker.esm.js";

export default {
  components: {
    SearchSelect,
    VueNumericInput,
    // Datepicker,
    DateSelect
  },
  data() {
    return {
      value1: 0,
      value2: 0,
      value3: 0,
      value4: 0,
      value5: 0
    };
  }
};
</script>

<style src="./assets/css/app.css"/>

<script>
import SelectDateRange from "./SelectDateRange.vue";
import SelectInformation from "./SelectInformation.vue";
import DownloadReport from "./DownloadReport.vue";

export default {
  name: "Stepper",
  components: {
    SelectDateRange,
    SelectInformation,
    DownloadReport,
  },
  data() {
    return {
      activeStep: 1,
      steps: [
        {
          label: "Select date range",
          number: 1,
        },
        {
          label: "Select information",
          number: 2,
        },
        {
          label: "Download report",
          number: 3,
        },
      ],
    };
  },
  methods: {
    handleNextBtnClick() {
      this.activeStep = this.activeStep + 1;
    },
    handleBackBtnClick() {
      this.activeStep = this.activeStep - 1;
    },
    handleStepLabelClick(step) {
      this.activeStep = step.number;
    },
  },
};
</script>

<template>
  <div class="stepper-container">
    <div
      :class="['step', `${step.number != steps.length ? 'expand' : ''}`]"
      v-for="(step, i) in steps"
      :key="i"
    >
      <div
        :class="[
          'step-number',
          `${activeStep === step.number ? 'active-step' : ''}`,
        ]"
        :id="'step-' + step.number"
      >
        <i v-if="step.number < activeStep" class="fa fa-check"></i>
        <span v-else>{{ step.number }}</span>
      </div>
      <div
        v-if="step.number != steps.length"
        :class="[
          'step-connector',
          `${activeStep > step.number ? 'completed-connector' : ''}`,
        ]"
      ></div>
      <div
        :class="[
          'step-label',
          `${activeStep === step.number ? 'active-label' : ''}`,
          `${activeStep > step.number ? 'completed-step' : ''}`,
          `${step.number === steps.length ? 'last-step-label' : ''}`,
        ]"
        @click="activeStep > step.number && handleStepLabelClick(step)"
      >
        {{ step.label }}
      </div>
    </div>
  </div>
  <div v-if="activeStep === 1">
    <SelectDateRange />
  </div>
  <div v-if="activeStep === 2">
    <SelectInformation />
  </div>
  <div v-if="activeStep === 3">
    <DownloadReport />
  </div>
  <div class="stepper-btn-container">
    <button
      v-if="activeStep !== 1 && activeStep !== 3"
      class="back-btn"
      @click="handleBackBtnClick()"
    >
      Back
    </button>
    <button
      v-if="activeStep !== 3"
      class="next-btn"
      @click="handleNextBtnClick()"
    >
      Next
    </button>
  </div>
  <div class="extra-info">
    <p>
      Your Blue Button report is presented in a Portable Document Format (PDF),
      which requires Adobe Reader for viewing and printing. To download the
      program, visit
      <a class="external-link"
        ><span>Adobe's website</span>
        <i class="fa fa-external-link" aria-hidden="true"></i></a
      >.
    </p>
    <p>
      Humana's participation in the Blue Button program does not imply
      endorsement by His or the U.S. government.
    </p>
  </div>
</template>

<style scoped>
.stepper-container {
  display: flex;
  justify-content: space-between;
  padding: 1em;
  width: 60%;
  margin: 1rem auto 2rem auto;
  position: relative;
}
.progress {
  position: absolute;
  top: 25px;
  left: 80px;
  height: 5px;
  margin: 0 auto;
  box-shadow: none;
  background-color: #c8c8c8;
  width: 80%;
}
.progress-bar {
  background-color: #5c9a1b;
  height: 5px;
  width: 0;
}
.step-number > span {
  background-color: #c8c8c8;
  color: white;
  padding: 0.7rem 1.1rem;
  border-radius: 50%;
  font-weight: bold;
}
.active-step span {
  background-color: #114a21;
  color: white;
  padding: 0.7rem 1.1rem;
  border-radius: 50%;
}
.step-number > i {
  background-color: #fff;
  color: #114a21;
  padding: 0.7rem;
  border-radius: 50%;
  border: 2px solid #114a21;
  margin-top: -8px;
}
.step {
  text-align: center;
  z-index: 2;
  position: relative;
  display: flex;
  align-items: center;
}
.expand {
  width: 100%;
}
.step-connector {
  width: 100%;
  height: 5px;
  background-color: #c8c8c8;
}
.completed-connector {
  background-color: #5c9a1b;
  transition: 0.3s all;
}
.step-label {
  color: #53575a;
  padding-top: 1.2rem;
  font-weight: bold;
  position: absolute;
  top: 18px;
  left: -35px;
}
.active-label {
  color: #114a21;
}
.completed-step {
  padding-top: 1.2rem;
  text-decoration: underline;
  cursor: pointer;
}
.last-step-label {
  width: 200px;
  left: -80px;
}
.stepper-btn-container {
  width: 60%;
  margin: 0 auto 3rem auto;
}
.next-btn {
  padding: 0.5rem 0.7rem;
  color: #fff;
  background-color: #5c9a1b;
  border: none;
  outline: none;
  border-radius: 3px;
  cursor: pointer;
}
.back-btn {
  padding: 0.5rem 0.7rem;
  color: #5c9a1b;
  background-color: #fff;
  border: 2px solid #5c9a1b;
  outline: none;
  border-radius: 3px;
  margin-right: 1rem;
  margin-left: 1.5rem;
  cursor: pointer;
  font-weight: bold;
}
.extra-info {
  width: 60%;
  margin: 0 auto;
}
.extra-info p {
  margin-bottom: 1.5rem;
}
.external-link {
  color: #007481;
  cursor: pointer;
}
.external-link span {
  font-weight: bold;
  text-decoration: underline;
  margin-right: 0.3rem;
}
.external-link i {
  font-size: 12px;
}
</style>

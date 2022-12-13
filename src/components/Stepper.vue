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
      progressValue: [0, 50, 100],
      progress: "",

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
      this.progress = `width: ${
        this.progressValue[this.activeStep - 1]
      }%; transition: .3s all;`;
    },
    handleBackBtnClick() {
      this.activeStep = this.activeStep - 1;
      this.progress = `width: ${
        this.progressValue[this.activeStep - 1]
      }%; transition: .3s all;`;
    },
    handleStepLabelClick(step) {
      this.activeStep = step.number;
      this.progress = `width: ${
        this.progressValue[this.activeStep - 1]
      }%; transition: .3s all;`;
    },
  },
};
</script>

<template>
  <div class="stepper-container">
    <div class="progress">
      <div
        class="progress-bar"
        role="progressbar"
        aria-valuenow="60"
        aria-valuemin="0"
        aria-valuemax="100"
        :style="progress"
      ></div>
    </div>
    <div class="step" v-for="(step, i) in steps" :key="i">
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
        :class="[
          'step-label',
          `${activeStep === step.number ? 'active-label' : ''}`,
          `${activeStep > step.number ? 'completed-step' : ''}`,
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
  flex-direction: row;
  justify-content: space-between;
  padding: 1em;
  width: 60%;
  margin: 0 auto;
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
  padding: 0.75rem;
  border-radius: 50%;
  border: 2px solid #114a21;
  margin-top: -8px;
}
.step {
  text-align: center;
  z-index: 2;
}
.step-label {
  color: #53575a;
  padding-top: 1rem;
  font-weight: bold;
}
.active-label {
  color: #114a21;
}
.completed-step {
  padding-top: 0.2rem;
  text-decoration: underline;
  cursor: pointer;
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
  border: 1px solid #5c9a1b;
  outline: none;
  border-radius: 3px;
  margin-right: 1rem;
  cursor: pointer;
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

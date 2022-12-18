<script>
export default {
  name: "DownloadReport",
};
</script>

<template>
  <div class="download-report-container">
    <h1>Your report is ready for you to download!</h1>
    <h2>Please take a moment to ensure your information is secure.</h2>
    <p>
      You are about to create a local copy of your protected health data on your
      computer or mobile device. Only share your information with people you
      trust, such as your healthcare provider or friends and family.
    </p>

    <p>You are now able to download your information.</p>
    <div class="download-report-btn-container">
      <button class="download-btn">
        <span>Download your Blue Button health report</span
        ><i class="fa fa-arrow-right" aria-hidden="true"></i>
      </button>

      <button class="return-btn">
        <span>Return to Blue Button main page</span
        ><i class="fa fa-arrow-right" aria-hidden="true"></i>
      </button>
    </div>
  </div>
</template>

<style scoped>
.download-report-container {
  padding: 1.5rem 1.5rem 0 1.5rem;
  width: 60%;
  margin: 0 auto;
}
.download-report-container h2 {
  color: #114a21;
}
.download-report-btn-container {
  display: flex;
  flex-direction: column;
}
.download-btn {
  padding: 0.7rem 1rem;
  color: #fff;
  width: fit-content;
  display: flex;
  align-items: center;
  background-color: #5c9a1b;
  font-size: 19px;
  border: none;
  outline: none;
  border-radius: 3px;
  cursor: pointer;
  margin-bottom: 1.2rem;
}
button i {
  margin-left: 0.5rem;
}
.return-btn {
  color: #007481;
  font-size: 18px;
  width: fit-content;
  display: flex;
  align-items: center;
  background-color: transparent;
  border: none;
  outline: none;
  cursor: pointer;
  font-weight: bold;
}
</style>

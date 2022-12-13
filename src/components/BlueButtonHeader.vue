<script>
export default {
  name: "BlueButtonHeader",
};
</script>

<template>
  <div class="header">
    <div>
      <a class="back-link">
        <i class="fa fa-arrow-left" aria-hidden="true"></i>
        <h4>Back to Myhealth</h4>
      </a>
    </div>
    <div class="blue-button-container">
      <img src="@/assets/download-icon.png" alt="download" />
      <h1>Blue Button</h1>
    </div>
  </div>
</template>

<style scoped>
.header {
  padding: 1.5rem;
  background-color: #f8f8f8;
}
.back-link {
  display: flex;
  align-items: center;
  color: #007481;
  width: fit-content;
  cursor: pointer;
}
.back-link h4 {
  margin: 0 0.5rem;
}
.blue-button-container {
  display: flex;
  align-items: center;
  margin: 1rem 0;
}
.blue-button-container img {
  width: 40px;
  height: 40px;
}
.blue-button-container h1 {
  color: #5c9a1b;
  margin: 0 0.5rem;
  font-weight: 300;
}
</style>

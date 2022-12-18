<script>
export default {
  name: "SelectInformation",
};
</script>

<template>
  <div class="select-info-container">
    <div class="blue-button-info">
      <h1>Blue Button</h1>
      <p>
        Blue Button makes it easy for you to download your protected health
        records. You can also obtain information about particular medical areas,
        including conditions and prescriptions.
      </p>

      <p>
        Blue Button enables you to easily share your health information with
        your healthcare provider, caregiver or other people you trust.
      </p>
    </div>

    <div class="select-report-info-container">
      <h2>Select your report information</h2>
      <div class="select-report-info">
        <p>
          <span>Current Condition</span>
          <i class="fa fa-question-circle" aria-hidden="true"></i>
        </p>
        <p class="notification-bar">
          <img src="@/assets/alarmbell.svg" alt="notification" /><span>
            There is no information to display in this section and it will not
            appear on your report.</span
          >
        </p>
        <div class="checkbox-field">
          <input
            type="checkbox"
            value="prescriptionHistory"
            id="prescriptionHistory"
          />
          <label for="prescriptionHistory"
            ><span>Prescription History</span>
            <i class="fa fa-question-circle" aria-hidden="true"></i
          ></label>
        </div>
        <div class="checkbox-field">
          <input type="checkbox" value="labHistory" id="labHistory" />
          <label for="labHistory"
            ><span>Lab History</span>
            <i class="fa fa-question-circle" aria-hidden="true"></i
          ></label>
        </div>
        <p>
          <span>Patient admission/Re-admission and ER visits</span>
          <i class="fa fa-question-circle" aria-hidden="true"></i>
        </p>
        <p class="notification-bar">
          <img src="@/assets/alarmbell.svg" alt="notification" /><span
            >There is no information to display in this section and it will not
            appear on your report.</span
          >
        </p>
      </div>
    </div>

    <div class="secure-info-container">
      <h2>Keep your information secure</h2>
      <div class="secure-info">
        <p>
          If you'd prefer additional security, you can protect your PDF with a
          password before you download it. This will ensure that your
          information is secure, and only people with your password will be able
          to open the file. Humana will NOT retain your password. Once you have
          entered a password, you can only open your download report by entering
          the same password.
        </p>
        <form>
          <h3>Do you wish to password protect your health record?</h3>
          <div class="radio-group">
            <div class="radio-field">
              <input
                type="radio"
                value="yes"
                id="yes"
                name="password-protect"
              />
              <label for="yes">Yes</label>
            </div>

            <div class="radio-field">
              <input type="radio" value="no" id="no" name="password-protect" />
              <label for="no">No</label>
            </div>
          </div>

          <p><span class="required">*</span> Required</p>

          <div class="password-field">
            <label for="create-password"
              >Create password <span class="required">*</span></label
            >
            <input type="password" value="" id="create-password" />
            <p class="input-info">
              Requirements: 6-15 case-sensitive letters or numbers, no spaces or
              special characters.
            </p>
          </div>
          <div class="password-field">
            <label for="confirm-password"
              >Confirm password <span class="required">*</span></label
            >
            <input type="password" value="" id="confirm-password" />
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
.select-info-container {
  padding: 1.5rem;
  width: 60%;
  margin: 0 auto;
}
.select-report-info-container {
  margin-bottom: 3rem;
}
.select-report-info-container h2,
.secure-info-container h2 {
  color: #114a21;
}
.select-report-info,
.secure-info {
  padding-left: 1.5rem;
}
.select-report-info i {
  color: #0062a6;
  margin-left: 0.3rem;
  font-size: 14px;
  cursor: pointer;
}
.checkbox-field {
  margin-bottom: 0.8rem;
}
.checkbox-field label {
  margin-left: 5px;
}
.notification-bar {
  background-color: #fcf6ee;
  width: fit-content;
  display: flex;
  align-items: center;
}
.notification-bar img {
  width: 15px;
  height: 15px;
  margin-right: 5px;
}
.radio-group {
  display: flex;
}
.radio-field {
  margin-right: 1rem;
}
.required {
  color: red;
  font-weight: bold;
}
.password-field {
  display: flex;
  flex-direction: column;
  margin-bottom: 1rem;
}
.password-field input {
  outline: none;
  border: 1px solid #707373;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  width: 20%;
}
.input-info {
  color: #53575a;
  font-size: 12px;
  margin: 0.2rem 0;
  font-weight: bold;
}
</style>

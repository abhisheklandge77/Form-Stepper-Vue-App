<script>
export default {
  name: "SelectDateRange",
};
</script>

<template>
  <div class="select-date-range-container">
    <div class="access-info">
      <h1>Access your health information in three easy steps:</h1>
      <p>1. Select dates</p>
      <p>2. Select your information</p>
      <p>3. Download a PDF of your data</p>
      <p>
        Blue Button makes it easy for you to download your protected health
        information. With just a few clicks, you can access a secure copy of
        your personal health report on your computer or mobile device. Note:
        health records are only available for Commercial, Humana One or Medicare
        medical plan members, not their dependents.
      </p>
    </div>
    <div class="get-info">
      <h2>Get the right information and protect it with a few simple steps:</h2>
      <p>
        <span>1. Check it</span> — Select the information you need within the
        time period allowed (up to one year).
      </p>
      <p>
        <span>2. Share it</span> — Only share your information with people you
        trust, such as your healthcare provider, caregiver or family members.
      </p>
      <p>
        Do you have questions about Blue Button? Read more about about it
        <a class="external-link"
          ><span>here</span>
          <i class="fa fa-external-link" aria-hidden="true"></i></a
        >.
      </p>
    </div>
    <div class="select-date-range-form">
      <h2>Select a date range</h2>
      <p>
        The Blue Button allows Commercial, Humana One or Medicare medical plan
        members to access their health information dating back a full 365 days.
      </p>
      <form>
        <div class="date-range-field">
          <input
            type="radio"
            value="past3Months"
            id="3months"
            name="date-range"
          />
          <label for="3months">Past 3 months</label>
        </div>

        <div class="date-range-field">
          <input
            type="radio"
            value="past6Months"
            id="6months"
            name="date-range"
          />
          <label for="6months">Past 6 months</label>
        </div>

        <div class="date-range-field">
          <input
            type="radio"
            value="past365Days"
            id="365days"
            name="date-range"
          />
          <label for="365days">Past 365 days</label>
        </div>

        <div class="date-range-field">
          <input
            type="radio"
            value="selectDaterange"
            id="selectdaterange"
            name="date-range"
          />
          <label for="selectdaterange">Select a date range</label>
        </div>
      </form>
    </div>
  </div>
</template>

<style scoped>
.select-date-range-container {
  width: 60%;
  margin: 0 auto;
  color: #3a3b3d;
}
.access-info {
  margin-bottom: 3rem;
}
.get-info {
  margin-bottom: 3rem;
}
.get-info span {
  font-weight: bold;
}
.get-info h2,
.select-date-range-form h2 {
  color: #114a21;
}
.select-date-range-form {
  margin-bottom: 1rem;
}
.date-range-field {
  margin-bottom: 1rem;
}
.date-range-field label {
  margin-left: 0.3rem;
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

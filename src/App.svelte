<script>
  let years = 0;
  let months = 0;
  let days = 0;

  let diffYear = 0;
  let diffMonth = 0;
  let diffDays = 0;

  const currDate = new Date();
  let currDay = currDate.getDate();
  let currMonth = currDate.getMonth() + 1;
  let currYear = currDate.getFullYear();

  diffYear = currYear - years;
  diffMonth = currMonth - months;
  diffDays = currDay - days;

  function calcYear() {
    if (years !== 0) {
      diffYear = Math.abs(currYear - years);
    }
  }

  function calcMonth() {
    if (months !== 0) {
      diffMonth = Math.abs(currMonth - months);
    }
  }

  function calcDay() {
    if (days !== 0) {
      diffDays = Math.abs(currDay - days);
    }
  }
</script>

<div class="card">
  <div class="day">
    <label class="dayLabel">Day</label>
    <input
      class="dayInput"
      type="number"
      placeholder="DD"
      style="width: 70px; height: 30px;"
      min="1"
      max="31"
      bind:value={days}
      on:input={calcDay}
    />
    <!--binding here-->
  </div>

  <div class="month">
    <label class="monthLabel">Month</label>
    <input
      class="monthInput"
      type="number"
      placeholder="MM"
      style="width: 90px; height: 30px;"
      min="1"
      max="12"
      bind:value={months}
      on:input={calcMonth}
    />
    <!--binding here-->
  </div>

  <div class="year">
    <label class="yearLabel">Year</label>
    <input
      class="yearInput"
      type="number"
      placeholder="YYYY"
      style="width: 70px; height: 30px;"
      min="1960"
      max="2100"
      bind:value={years}
      on:input={calcYear}
    />
    <!--binding here-->
  </div>
</div>

<br />
<hr />

<div class="calculations">
  <div class="Y">
    <span style="color: purple;">{diffYear}</span> years <!--binding here-->
  </div>
  <div class="M">
    <span style="color: purple;">{diffMonth}</span> months <!--binding here-->
  </div>
  <div class="D">
    <span style="color: purple;">{diffDays}</span> days <!--binding here-->
  </div>
</div>

<div class="attribution">
  Challenge by <a
    href="https://www.frontendmentor.io?ref=challenge"
    target="_blank">Frontend Mentor</a
  >. Coded by <a href="#">Tanvi</a>.
</div>

<style>
  .card {
    width: 500px;
    height: 400px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    box-shadow: 0 4px 8px 0 rgba(152, 115, 115, 0.2);
    transition: 0.3s;
    border-radius: 15px;
    margin: auto;
  }

  .day {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }
  .dayLabel,
  .monthLabel,
  .yearLabel {
    position: relative; /* Position label absolutely */
    top: 0; /* Place label at the top */
    left: 0; /* Place label at the left */
    padding-bottom: 10px;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    color: grey;
  }

  .month {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  .year {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  .calculations {
    width: 100%;
    padding: 20px;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    font-size: large;
    font-style: italic;
  }

  .Y,
  .M,
  .D {
    font-weight: bold;
  }

  .attribution {
    padding: 50px;
  }
</style>

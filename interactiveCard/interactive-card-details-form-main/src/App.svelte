<script>
  let holderName = "";
  let number = "";
  let month = "";
  let year = "";
  let cvc = "";

  let inputvalue = "";

  function handleInputFunction(event) {
    inputvalue = event.target.value;

    if (inputvalue.trim() === "") {
      alert("input field cannot be empty");
    }
  }

  function handleConfirmClick() {
    const confirmed = confirm("are you sure?");
    if (confirmed) {
      document.getElementById("greenTick").style.display = "flex";
      
    }
  }
</script>

<body>
  <main style="display: flex;">
    <div class="card">
      <div class="cardFront">
        <img
          src="interactive-card-details-form-main\images\bg-card-front.png"
        />
        <input class="displayCardNumber" bind:value={number} readonly />
      </div>

      <div class="cardBack">
        <img src="interactive-card-details-form-main\images\bg-card-back.png" />
        <input class="displayCardHolderName" bind:value={holderName} readonly />
      </div>
    </div>

    <div>
      <div>
        <label class="cardHolder">cardholder name</label>
        <input
          class="cardHolderInput"
          type="text"
          placeholder="e.g. Jane Appleseed"
          bind:value={holderName}
          on:blur={handleInputFunction}
        />
      </div>

      <div>
        <label class="cardNumber">card number</label>
        <input
          class="cardNumberInput"
          type="text"
          placeholder="e.g. 1234 5678 0000"
          bind:value={number}
          on:blur={handleInputFunction}
        />
      </div>

      <div class="exipryAndCVCContainer">
        <div class="expiryInputContainer">
          <label class="expiryDate">exp. date (MM/YY)</label>
          <div class="expiryInputs">
            <input
              class="monthInput"
              type="number"
              placeholder="MM"
              bind:value={month}
              on:blur={handleInputFunction}
            />
            <input
              class="yearInput"
              type="number"
              placeholder="YY"
              bind:value={year}
              on:blur={handleInputFunction}
            />
          </div>
        </div>

        <div class="cvcContainer">
          <label class="cvcLabel">cvc</label>
          <input
            class="cardCVCInput"
            type="number"
            placeholder="e.g. 123"
            bind:value={cvc}
            on:blur={handleInputFunction}
          />
        </div>
      </div>
      <!-- <a href="/confirmation">
        <button class="confirmButton">confirm</button>
      </a> -->

      <button class="confirmButton" on:click={handleConfirmClick}
        >confirm</button
      >
      <img
        src="interactive-card-details-form-main\images\green_tick.jpg"
        id="greenTick"
        style="display: none;"
        class="confirmation"
      />
    </div>
  </main>
</body>

<!--responsive pg
the input on the img cannot be edited unless its corresponding input on the other size is edited-->

<style>
  .confirmation {
    border-radius: 50%;
    width: 90px; /* Adjust width as desired */
    height: 90px;
  }
  .confirmButton {
    width: 100%;
    margin-top: 50%;
    padding: 10px;
    margin: 20px;
  }

  .card {
    position: relative;
  }

  .cardFront {
    position: relative;
  }

  .displayCardNumber {
    position: absolute;
    bottom: 23%;
    left: 20px;
    width: 80%;
    height: 10%;
    background-color: rgba(0, 0, 0, 0.3); /* Set semi-transparent background */
    color: white; /* Text color for visibility */
    border: none;
    font-size: large;
    transition: opacity 0.3s ease-in-out; /* Smooth transition on hover */
  }

  .displayCardHolderName {
    position: absolute;
    bottom: 53%;
    left: 20px;
    width: 30%;
    height: 4%;
    background-color: rgba(0, 0, 0, 0.3); /* Set semi-transparent background */
    color: white; /* Text color for visibility */
    border: none; /* Remove border */
    overflow: hidden;
    font-size: medium;
    transition: opacity 0.3s ease-in-out; /* Smooth transition on hover */
  }

  .card:hover .displayCardNumber {
    opacity: 1;
  }

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  .cardHolder,
  .cardNumber,
  .expiryDate,
  .cvcLabel {
    display: flex;
    align-items: center;
    margin-bottom: 10px;
    margin-top: 10px;
  }

  label {
    display: block;
    margin-bottom: 5px;
    font-weight: bold;
    font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
      "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
    margin-left: 20px;
  }
  input {
    width: 100%;
    padding: 8px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-shadow: inset 0 1px 2px rgba(197, 34, 34, 0.1);
    font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS",
      sans-serif;
    box-shadow: inset 0 1px 2px rgba(182, 0, 0, 0.471);
    font-size: large;
    margin-left: 20px;
  }

  .expiryDate,
  .cvcLabel {
    width: 40%;
  }

  .expiryInputContainer {
    display: flex;
  }

  .yearInput,
  .monthInput {
    width: 55%;
    /* margin-right: 10px; */
    margin-top: 20px;
  }

  .exipryAndCVCContainer {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }

  @media only screen and (max-width: 844px) {
    .displayCardNumber {
      position: absolute;
      bottom: 17%;
      left: 10px;
      width: 80%;
      height: 7%;
      background-color: rgba(
        0,
        0,
        0,
        0.3
      ); /* Set semi-transparent background */
      color: white; /* Text color for visibility */
      border: none;
      font-size: large;
      transition: opacity 0.3s ease-in-out; /* Smooth transition on hover */
    }

    .displayCardHolderName {
      position: absolute;
      bottom: 62%;
      left: 10px;
      width: 30%;
      height: 2%;
      background-color: rgba(
        0,
        0,
        0,
        0.3
      ); /* Set semi-transparent background */
      color: white; /* Text color for visibility */
      border: none; /* Remove border */
      overflow: hidden;
      font-size: medium;
      transition: opacity 0.3s ease-in-out; /* Smooth transition on hover */
    }
    .card {
      flex-direction: column; /* Stack cards vertically */
      align-items: center; /* Center-align cards */
      margin-bottom: 20px; /* Add space between cards and form */
    }

    .cardFront,
    .cardBack {
      width: 100%; /* Full width for card fronts and backs */
      margin-bottom: 20px; /* Add space between cards */
    }

    .cardFront img,
    .cardBack img {
      width: 100%; /* Ensure card images take full width */
    }

    .cardBack {
      order: -1; /* Move card back to top in column layout */
    }

    .exipryAndCVCContainer {
      flex-direction: column; /* Stack expiry and CVC vertically */
      align-items: center; /* Center-align inputs */
    }

    .expiryDate,
    .cvcLabel {
      width: 100%; /* Full width for expiry date and CVC labels */
    }

    .expiryInputs {
      flex-direction: column; /* Stack month and year inputs vertically */
      align-items: center; /* Center-align inputs */
    }

    .yearInput,
    .monthInput {
      width: 100%; /* Full width for month and year inputs */
      margin-top: 10px; /* Add spacing */
    }
  }
</style>

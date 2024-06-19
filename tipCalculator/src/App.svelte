<script>
  let tipAmount = 0;
  let totalbill = 0;
  let tipPercentage = 0;

  function handleReset() {
    window.location.reload();
  }

  function calculateTip(tipPercentage) {
    
    let billInput = document.getElementById('billInput');
    let billAmount = parseFloat(billInput.getAttribute('value'));

    let numberOfPeopleinput = document.getElementById('numberOfPeopleInput');
    let numberOfPeople = parseInt(numberOfPeopleinput.getAttribute('value'));

    if (isNaN(billAmount) || isNaN(numberOfPeople) || billAmount <= 0 || numberOfPeople <=0 ) {
      alert("enter valid values for bill amount and number of people");
      return;
    }

    let tipPerPerson = (billAmount*tipPercentage)/100/numberOfPeople;

    let totalPerPerson = (billAmount/numberOfPeople) + tipPerPerson;

    let totalTip = tipPerPerson*numberOfPeople;
    let total = billAmount + totalTip;

    document.getElementById('tipAmtInput').setAttribute('value', tipPerPerson.toFixed(2));
    document.getElementById('totalBillInput').setAttribute('value', totalPerPerson.toFixed(2));
    tipAmount = totalTip;
    totalbill = total;
  }

</script>

<main>
  <div class="main_card">
    <div class="billContainer">
      <label class="billLabel">Bill</label>
      <span class="dollarSign">$</span>
      <input
        id="billInput"
        type="number"
        class="billInput"
        placeholder="enter amount"
        min="0"
      />
    </div>

    <div class="half_card">
      <div class="half_card_container">
        <label class="tipAmtLabel"
          >Tip Amount <span class="perPerson"> / person</span></label
        >
        <input
          id="tipAmtInput"
          class="tipAmtInput"
          bind:value={tipAmount}
          readonly
        />

        <label class="totalBillLabel">Total</label>
        <input
          id="totalBillInput"
          class="totalBillInput"
          bind:value={totalbill}
          readonly
        />
      </div>
      <!-- <form id="resetForm">
        <input class="resetButton" type="reset" value="Reset" />
      </form> -->

      <button class="resetButton" on:click={handleReset}>Reset</button>
    </div>

    <div class="selectTipContainer">
      <label>Select Tip %</label>
      <div class="tipButtons">
        <button class="5PercentButton" on:click={() => calculateTip(5)}>5%</button>
        <button class="10PercentButton" on:click={() => calculateTip(10)}>10%</button>
        <button class="15PercentButton" on:click={() => calculateTip(15)}>15%</button>
        <button class="25PercentButton" on:click={() => calculateTip(25)}>25%</button>
        <button class="50PercentButton" on:click={() => calculateTip(50)}>50%</button>
      </div>
    </div>

    <div class="numberOfPeopleContainer">
      <label class="numberOfPeopleLabel">Enter the number of people</label>
      <input id="numberOfPeopleInput" type="number" class="numberOfPeopleInput" />
      <img class="userImg" src="tip-calculator-app-main\images\user.png" />
    </div>
  </div>
</main>

<style>
  .main_card {
    background-color: rgb(255, 255, 255);
    color: rgb(0, 0, 0);
    width: 900px;
    height: 400px;
    border-radius: 25px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    padding: 20px;
    margin: 20px;
    display: flex;
    justify-content: space-between;
    position: relative;
  }

  .half_card {
    background-color: rgb(0, 128, 53);
    flex: 0.5;
    border-radius: 25px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    padding: 10px;
    margin: 5px;
    position: relative;
    color: white;
  }

  /* .half_card {
    justify-self: flex-end;
  } */

  .half_card_container {
    margin-top: 80px;
    margin-left: 40px;
    margin-right: 31px;
    display: flex;
    /* position: absolute; */
    font-weight: bold;
    font-size: larger;
    flex-direction: column;
  }

  .resetButton {
    width: 100%;
    margin-top: 28px;
    background-color: #1a2a1b;
    font-family: Georgia, "Times New Roman", Times, serif;
    font-size: large;
    border-radius: 10px;
    border: none;
    height: 39px;
  }

  .tipAmtLabel {
    margin-right: 300px;
  }

  .totalBillLabel {
    margin-right: 300px;
  }

  .tipAmtInput,
  .totalBillInput {
    /* flex: 1; */
    /* width: 80%; */
    text-align: right;
    /* padding-left: 5px; */
    border: none;
    border-radius: 5px;
    background-color: transparent;
    font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
    font-size: larger;
    /* position: relative; */
    /* margin-left: 20px; */
    width: 50%;
    /* display: flex; */
    /* align-items: center; */
    margin-bottom: 10px;
    margin-left: 50%;
    align-self: flex-start;
  }
  /* 
  .tipAmtContainer, .totalBillContainer {
    display: flex;
    align-items: center;
    margin-bottom: 10px;
  } */

  .billContainer {
    position: absolute;
    /* top: 41.2%;
    right: 20px; */
    /*transform: translateY(-50%); */
    top: 113px;
    right: 20px;
    align-items: center;
    display: flex;
    font-size: larger;
    flex-direction: column;
    margin-right: 80px;
    /* position: absolute; */
  }

  .billLabel {
    /* display: block; */
    /* margin: 50px;
    position: relative; */
    margin-bottom: 5px;
    margin-right: 229px;
    font-weight: bold;
  }

  .billInput {
    flex: 1;
    width: 80%;
    text-align: right;
    padding-left: 5px;
    border: none;
    border-radius: 5px;
    font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
    font-size: large;
    position: relative;
    background-color: gainsboro;
    outline: none;
    color: #000000;
  }

  .billInput::placeholder {
    /* For modern browsers */
    color: #000000;
  }

  .selectTipContainer {
    position: absolute;
    top: 190px;
    right: 7%;
    align-items: center;
    display: flex;
    font-size: medium;
    flex-direction: column;
    font-weight: bold;
    margin-top: 20px;
    font-size: large;
  }

  .selectTipContainer label {
    margin-bottom: 10px;
    margin-right: 190px;
  }

  .tipButtons {
    /* display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px; */

    display: flex;
    gap: 10px;
    /* flex-direction: row; */
    padding: 5px;
  }

  .tipButtons button {
    /* width: 100%; Buttons take full width of their container */
    padding: 10px;
    font-size: 16px;
    border: none;
    background-color: rgb(0, 128, 53);
    color: white;
    cursor: pointer;
    border-radius: 5px;
    flex: 1;
  }

  .tipButtons button:hover {
    background-color: #45a049;
  }

  .dollarSign {
    position: absolute;
    left: 5px;
    top: 60%;
    transform: translateY(-15%);
    font-size: large;
    color: #000000;
  }

  .numberOfPeopleContainer {
    position: absolute;
    top: 330px;
    right: 0.01px;
    display: flex;
    align-items: center;
    font-size: larger;
    flex-direction: column;
    margin-right: 80px;
  }

  .numberOfPeopleLabel {
    margin-bottom: 5px;
    margin-right: 10px;
    font-weight: bold;
  }

  .numberOfPeopleInput {
    flex: 1;
    width: 80%;
    text-align: right;
    padding-left: 5px;
    border-radius: 5px;
    font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
    font-size: larger;
    position: relative;
    border: none;
    background-color: gainsboro;
    outline: none;
    color: #000000;
  }

  .perPerson {
    font-size: smaller;
    color: rgb(180, 180, 180);
    position: relative;
    top: -2px;
    display: flex;
    flex-direction: column;
    margin-right: 41px;
  }

  .userImg {
    width: 20px;
    height: 20px;
    position: absolute;
    /* top: calc(60%-10px);
    right: 260px; */
    top: calc(100% - 24px); /* Position it just below the input */
    right: 260px; /*
    /* margin-left: 8px;
    vertical-align: middle; */

    /* left: 15px; */
    /* top: 45%; */
    /* transform: translateY(-50%);
    transform: translateX(-600%); */
    /* vertical-align: middle; */
  }
</style>

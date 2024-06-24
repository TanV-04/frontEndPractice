<script>
  function validateEmail(email) {
    const re =
      /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
    return re.test(String(email).toLowerCase());
  }

  function handleEmailinput(event) {
    const emailInput = event.target;
    const email = emailInput.value;
    const emailContainer = emailInput.parentElement;

    if (validateEmail(email)) {
      emailContainer.classList.remove("error");
      // emailContainer.nextElementSibling.textContent = "";
    } else {
      emailContainer.classList.add("error");
      emailContainer.nextElementSibling.textContent =
        "Please enter a valid email address.";
    }
  }

  function handleSubscribeClick(event) {
    const emailInput = document.querySelector(".rounded-md");
    const email = emailInput.value;
    const emailContainer = emailInput.parentElement;
    if (!email) {
      emailContainer.classList.add("error");
      emailContainer.nextElementSibling.textContent =
        "Please enter your email address.";
      event.preventDefault(); // Prevent form submission
    } else if (!validateEmail(email)) {
      emailContainer.classList.add("error");
      emailContainer.nextElementSibling.textContent =
        "Please enter a valid email address.";
      event.preventDefault(); // Prevent form submission
    } else {
      console.log("submitted");
    }
  }
</script>

<body class="flex flex-col h-screen">
  <main class="flex-grow flex flex-col items-center px-4">
    <div class="bg-white shadow-md rounded-lg p-6 max-w-md text-black">
      <h1 class="poppins-font text-xl font-bold">Stay Updated!</h1>

      <div class="text-left py-4">
        <p>Join 60,000+ product managers receiving monthly updates on:</p>
        <!-- <p>Product discovery and building what matters</p>
        <p>Measuring to ensure updates are a success</p>
        <p>And much more!</p> -->
        <ul class="pl-1 py-4">
          <li>
            <span>&#10003</span>Product discovery and building what matters
          </li>
          <li><span>&#10003</span>Measuring to ensure updates are a success</li>
          <li><span>&#10003</span>And much more!</li>
        </ul>
      </div>

      <div class="flex flex-col space-y-2">
        <label class=" email-label text-left">Enter your email</label>
        <input
          class="rounded-md px-3 py-2 border border-gray-300 focus:outline-none focus:ring-1 focus:ring-blue-500 text-white"
          type="text"
          placeholder="abc@gmail.com"
          on:blur={() => handleEmailinput(event)}
        />
        <span class="error-messae text-red-500"></span>
      </div>

      <div class="sub-button py-6 text-white">
        <button class="w-full" on:click={() => handleSubscribeClick(event)}
          >Subscribe to monthy newsletter!</button
        >
      </div>
    </div>
  </main>

  <footer class="bg-white-900 text-center p-100 py-4">
    Challenge by <a
      href="https://www.frontendmentor.io?ref=challenge"
      target="_blank">Frontend Mentor</a
    >.
  </footer>
</body>

<style>
  .poppins-font {
    font-family: "Poppins", sans-serif;
    font-weight: 400;
    font-style: normal;
  }

  .email-label {
    font-size: medium;
  }
</style>

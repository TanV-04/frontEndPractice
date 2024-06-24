<script>
</script>

<body class="flex flex-col h-screen">
  <header></header>

  <main class="flex-grow flex flex-col items-center px-4">
    <div class="bg-black shadow-md rounded-lg p-6 w-full max-w-lg">
      <img src="src\assets\image-omelette.jpeg" />
      <h1
        class="playwrite-font text-4xl font-extrabold dark:text-black mb-8 mt-8"
      >
        Simple Omelette Recipe
      </h1>

      <h2 class="text-left px-4 py-2 md:px-4 md:py-4 lg:px-4 lg:py-4 raleway">
        An easy and quick dish, perfect for any meal. This classic omelette
        combines beaten eggs cooked to perfection, optionally filled with your
        choice of cheese, vegetables, or meats.
      </h2>

      <div class="px-4 py-4 raleway">
        <div
          class="prep-time bg-gray-100 text-left px-4 py-2 rounded shadow-sm md:px-4 md:py-4 lg:px-4 lg:py-4"
        >
          <h2 class="py-2">Preparation time</h2>

          <ul class="list-style-none">
            <li>
              <strong>Total</strong>: Approximately 10 minutes
            </li>
            <li>
              <strong>Preparation</strong>: 5 minutes
            </li>
            <li>
              <strong>Cooking</strong>: 5 Minutes
            </li>
          </ul>
        </div>

        <div class="text-left">
          <h2 class="text-left py-4 text-3xl font-bold text-red-500">
            Ingredients
          </h2>
          <ul class="list-style-none-white">
            <li>2-3 large eggs</li>
            <li>Salt, to taste</li>
            <li>Pepper, to taste</li>
            <li>1 tablespoon of butter or oil</li>
            <li class="w-full">
              Optional fillings: cheese, diced vegetables, cooked <span
                class="pl-4"
              >
                meats, herbs</span
              >
            </li>
          </ul>
        </div>
        <hr class="mt-5" />

        <div class="text-left">
          <h2 class="text-left py-4 text-3xl font-bold text-red-500">
            Instructions
          </h2>
          <ol class="list-decimal pl-4">
            <li>
              <strong>Beat the eggs</strong> In a bowl, beat the eggs with a pinch
              of salt and pepper until they are well mixed. You can add a tablespoon
              of water or milk for a fluffier texture.
            </li>

            <li class="mt-4">
              <strong>Heat the pan</strong> Place a non-stick frying pan over medium
              heat and add butter or oil.
            </li>

            <li class="mt-4">
              <strong>Cook the omelette</strong>: Once the butter is melted and
              bubbling, pour in the eggs. Tilt the pan to ensure the eggs evenly
              coat the surface.
            </li>

            <li class="mt-4">
              <strong>Add fillings (optional)</strong>: When the eggs begin to
              set at the edges but are still slightly runny in the middle,
              sprinkle your chosen fillings over one half of the omelette.
            </li>

            <li class="mt-4">
              <strong>Fold and serve</strong>: As the omelette continues to
              cook, carefully lift one edge and fold it over the fillings. Let
              it cook for another minute, then slide it onto a plate.
            </li>

            <li class="mt-4">
              <strong>Enjoy</strong>: Serve hot, with additional salt and pepper
              if needed.
            </li>
          </ol>
        </div>
        <hr class="mt-5" />

        <div class="text-left">
          <h2 class="text-left py-4 text-3xl font-bold text-red-500">
            Nutrition
          </h2>
          <p>
            The table below shows nutritional values per serving without the
            additional fillings:
          </p>

          <div
            class="table-div mt-8 mb-8 w-full max-w-sm bg-white shadow-md rounded-lg"
          >
            <table>
              <tbody>
                <tr>
                  <td class="text-left px-4 py-2">Calories</td>
                  <td class="text-left py-2"><strong>277kcal</strong></td>
                </tr>

                <tr>
                  <td class="text-left px-4 py-2">Carbs</td>
                  <td class="text-left py-2"><strong>0g</strong></td>
                </tr>

                <tr>
                  <td class="text-left px-4 py-2">Protein</td>
                  <td class="text-left py-2"><strong>20g</strong></td>
                </tr>

                <tr>
                  <td class="text-left px-4 py-2">Fat</td>
                  <td class="text-left py-2"><strong>22g</strong></td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
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
  tr {
    border-bottom: 1px solid #ddd; /* Adjust border style as needed */
  }

  ul.list-style-none-white li::before {
    content: "•";
    color: rgb(255, 255, 255);
    margin-right: 10px;
  }

  ul.list-style-none li::before {
    content: "•";
    color: rgb(0, 0, 0);
    margin-right: 10px;
  }
  .playwrite-font {
    font-family: "Playwrite IT Moderna", cursive;
    font-optical-sizing: auto;
    font-weight: bold;
    font-style: normal;
  }

  img {
    border-radius: 5px;
  }

  .prep-time {
    color: black;
  }

  .prep-time h2 {
    color: rgb(187, 0, 0);
    font-weight: bold;
    font-size: medium;
  }

  .raleway {
    font-family: "Raleway", sans-serif;
    font-optical-sizing: auto;
  }

  .table-div {
    color: black;
  }

  table {
    width: 100%;
    border-collapse: collapse;
  }
</style>

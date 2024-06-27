<script>
  import svelteLogo from "./assets/svelte.svg";
  import letter from "./assets/letter.svg";
  import Counter from "./lib/Counter.svelte";
  import { get } from "svelte/store";

  let word = "";
  let definition = "";

  async function getWord() {
    const url = "https://random-word-api.herokuapp.com/word";

    try {
      // fetch the word
      const defUrl = await fetch(url);
      const w = await defUrl.json();

      // fetch the definition
      // const retrieveDef =
      //   "https://api.dictionaryapi.dev/api/v2/entries/en/${word}";
      // const waitDef = await fetch(retrieveDef);
      // const receiveDef = await waitDef.json();

      const definition = "https://www.google.com/search?q=define+${word}";

      word = w;
      // definition = receiveDef[0];
    } catch (error) {
      console.log(error);
    }
  }

  getWord();
</script>

<main>
  <header>
    <div>
      <h1 class="font-bold montserrat-font">{word}</h1>

      <h2 class="py-4"><a href="https://www.google.com/search?q=define+{word}" target="_blank">See definition on Google</a></h2>

      <button on:click={getWord}>Another Word</button>
    </div>
  </header>
</main>

<style>
  .montserrat-font {
    font-family: "Montserrat", sans-serif;
  }
</style>
<template>
  <div>
    Jokes
  </div>
</template>

<script>
import axios from "axios";

import Joke from "../../components/Joke";

export default {

  data() {
    return {
      jokes: []
    }
  },

  async created() {
    const config = {
      "Accept": "application/json"
    }

    try {
      const res = await axios.get(
        "https://icanhazdadjoke.com/search",
        config
      );
      this.data = res.data.results;
    } catch (err) {
      console.log(err);
    }

  },

  head() {
    return {
      title: "Dad Jokes",
      meta: [
        {
          hid: "description",
          name: "descriptions",
          content: "The best place for corny dad jokes"
        }
      ]
    };
  }
}
</script>

<style>

</style>
<template>
  <div>
    <nuxt-link
      to="/jokes"
      class="link"
    >
      Back to Jokes
    </nuxt-link>
    <h2>
      "{{ joke }}"
    </h2>
    <small>
      Joke ID: {{ $route.params.id }}
    </small>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      joke: {}
    }
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };
    try {
      const res = await axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      );
      this.joke = res.data.joke;
    } catch (err) {
      console.log(err);
    }
  }
}
</script>

<style>
  h2 {
    font-style: italic;
    padding: 1rem;
    margin-bottom: 1rem;
    padding-bottom: 1rem;
    border-bottom: 1px dotted #ccc;
  }

  small {
    font-size: 10px;
  }
</style>

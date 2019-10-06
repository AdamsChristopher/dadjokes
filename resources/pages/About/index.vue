<template>
  <div>
    <h1>
      About DadJokes
    </h1>
    <p>
      This an app that displays corny dad jokes.
    </p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "About the app",
      meta: [
        {
          hid: "description",
          name: "descriptions",
          content: "The best place for corny dad jokes"
        }
      ]
    };
  }
};
</script>

<style>

</style>
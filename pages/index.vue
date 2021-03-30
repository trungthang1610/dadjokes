<template>
  <div>
    <h2>Welcome to the best corny dad jokes app on the web</h2>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data() {
    return {
      title: 'AAAa',
    }
  },
  head() {
    return {
      title: 'Welcome To DadJokes',
      meta: [
        {
          hid: 'description',
          name: 'descripion',
          content: 'Best place for the corny dad jokes',
        },
      ],
    }
  },
})
</script>

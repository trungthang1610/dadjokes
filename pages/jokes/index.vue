<template>
  <div>
    <SearchJoke @search-text="searchJoke" />
    <Joke
      v-for="joke in jokes"
      :id="joke.id"
      :key="joke.id"
      :joke="joke.joke"
    />
  </div>
</template>

<script>
import axios from 'axios'
import Joke from '../../components/Joke.vue'
import SearchJoke from '../../components/SearchJoke.vue'

export default {
  components: {
    Joke,
    SearchJoke,
  },
  scrollToTop: true,
  data() {
    return {
      jokes: [],
    }
  },
  head() {
    return {
      title: 'DadJokes',
      meta: [
        {
          hid: 'description',
          name: 'descripion',
          content: 'Best place for the corny dad jokes',
        },
      ],
    }
  },
  async created() {
    const config = {
      headers: {
        Accept: 'application/json',
      },
    }

    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config)

      this.jokes = res.data.results
    } catch (err) {
      console.log(err) // eslint-disable-line no-console
    }
  },
  methods: {
    async searchJoke(text) {
      const config = {
        headers: {
          Accept: 'application/json',
        },
      }

      try {
        const res = await axios.get(
          `https://icanhazdadjoke.com/search?term=${text}`,
          config
        )

        this.jokes = res.data.results
      } catch (err) {
        console.log(err) // eslint-disable-line no-console
      }
    },
  },
}
</script>

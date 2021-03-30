<template>
  <div>
    <form @submit.prevent="onSubmit">
      <input v-model="text" type="text" placeholder="Search Joke..." />
      <input type="submit" value="Search" />
    </form>
  </div>
</template>

<script>
export default {
  name: 'SearchJoke',
  data() {
    return {
      text: '',
    }
  },
  methods: {
    onSubmit() {
      this.$emit('search-text', this.text)
      this.text = ''
    },
  },
}
</script>

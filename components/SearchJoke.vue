<template>
  <div>
    <form @submit.prevent="onSubmit">
      <input v-model="text" type="text" placeholder="Search Joke..." />
      <input type="submit" value="Search" />
    </form>
  </div>
</template>

<script>
import { required, minLength } from 'vuelidate/lib/validators'

export default {
  name: 'SearchJoke',
  validate: {
    text: {
      required,
      minlength: minLength(4),
    },
  },
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

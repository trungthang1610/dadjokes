<template>
  <div>
    <a-form :form="form" :layout="formLayout" @submit.prevent="onSubmit">
      <a-form-item>
        <a-input v-model="text" type="text" placeholder="Search Joke..." />
      </a-form-item>
      <a-form-item
        ><a-button html-type="submit" type="primary"
          >Search</a-button
        ></a-form-item
      >
    </a-form>
  </div>
</template>

<script>
export default {
  name: 'SearchJoke',
  data() {
    return {
      text: '',
      formLayout: 'inline',
      form: this.$form.createForm(this, { name: 'coordinated' }),
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

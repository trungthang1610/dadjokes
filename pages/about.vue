<template>
  <div>
    <h1>About DadJokes</h1>
    <p>This is an app display corny dad jokes</p>
  </div>
</template>

<script>
export default {
  name: 'About',
  head() {
    return {
      title: 'About The App',
      meta: [
        {
          hid: 'description',
          name: 'descripion',
          content: 'Best place for the corny dad jokes',
        },
      ],
    }
  },
}
</script>

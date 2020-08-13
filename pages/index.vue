<template>
  <div class="container">
    <h1 class="title">
      {{
        Object.keys(coms[0])[0].charAt(0).toUpperCase() +
        Object.keys(coms[0])[0].slice(1)
      }}
    </h1>
    <div class="w-25% alert alert-primary" role="alert">
      {{ coms[0].introduction }}
    </div>
    <div class="container"></div>
  </div>
</template>

<script>
export default {
  async fetch() {
    this.coms = await this.$content('coms').fetch()
  },
  // async asyncData({ $content }) {
  //   const page = await $content('hello').fetch()

  //   return {
  //     page,
  //   }
  // },
  data() {
    return {
      coms: [],
      q: '',
    }
  },
  layout: 'coffee',
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: block;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
  text-align: center;
  align-items: center;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>

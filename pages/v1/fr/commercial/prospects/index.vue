<template>
  <div class="container">
    <h5 class="title">
      Comment créer un prospect ?
    </h5>
    <div
      v-for="item in coms[0].prospects.create"
      :key="item.index"
      class="w-25% alert alert-primary"
      role="alert"
    >
      * {{ item }}
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

<template>
  <section>
    <h1>Kanye Quotes</h1>
    <p>"{{ info }}"</p>
    <p>-kanye west</p>
    <button @click="getQuote">Another One</button>
  </section>
</template>

<script>
import axios from "axios"
export default {
  data() {
    return {
      info: null
    }
  },
  methods: {
    getQuote() {
      axios.get('https://api.kanye.rest').then((res) => {
        console.log(res.data)
        this.info = res.data.quote
      })
    }
  },
  mounted() {
    this.getQuote()
  }
}

</script>

<style>

</style>

<template>
  <div class="quote_container">
    <app-quote v-for="(quote, index) in quotes" :key="index" @click.native="removeQuote(index)">
      <p>{{ quote }}</p>
    </app-quote>
  </div>
</template>

<script>
import Quote from './Quote'

export default {
  props: ['quotes'],
  components: {
    appQuote: Quote
  },
  methods: {
    removeQuote(index) {
      this.$emit('removeQuote', index);
    }
  }
}
</script>

<style scoped>
  .quote_container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
  }

</style>


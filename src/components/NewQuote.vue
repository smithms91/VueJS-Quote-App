<template>
    <form>
        <label>Quote</label>
        <textarea rows="3" v-model="quote"></textarea>
        <button @click.prevent="createNew">Add Quote</button>
    </form>
</template>

<script>

export default {
  data: function() {
    return {
      quote: ''
    }
  },
  methods: {
    createNew() {
      this.$emit('quoteAdded', this.quote);
      this.quote = '';
    }
  }
}
</script>

<style scoped>
  form {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  textarea {
    width: 30%;
    margin: .5rem;
    border: 1px solid black;
    border-radius: 5px;
    height: 100px;
    padding: 1rem;
    font-size: 20px;
  }

  button {
    padding: .5rem;
    background-color: #e12c3f;
    border-radius: 5px;
    color: white;
    box-shadow: 1px 2px 5px rgba(0,0,0,.25);
  }
</style>


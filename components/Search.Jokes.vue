<template>
  <div class="action-bar">
    <form @submit.prevent="onSubmit">
      <input type="text" v-model="text" placeholder="Search Jokes...">
      <input type="submit" value="Search Jokes">
    </form>
    <button @click="clearSearch" class="clear">Clear</button>
  </div>
</template>

<script>
export default {
  name: 'SearchJokes',
  data () {
    return {
      text: ''
    }
  },
  methods: {
    onSubmit () {
      this.$emit('search-text', this.text)
      this.text = ''
    },
    clearSearch () {
      this.$emit('search-text', '')
    }
  }
}
</script>

<style>
  .action-bar {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>

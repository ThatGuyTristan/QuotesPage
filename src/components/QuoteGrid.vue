<template>
  <div class="row">
    <appQuote @click.native="deleteQuote(index)" v-for="(quote, index) in quotes" :key="index">
      {{ quote }}
    </appQuote>
  </div>
</template>

<script>
import Quote from "./Quote.vue"

export default {
  props: ['quotes'],
  components: { appQuote: Quote },
  methods: {
    deleteQuote(index) {
      this.$emit('quoteDeleted', index);
    }
  }
}
</script>

<style scoped>

</style>

<template>
  <div class="text-center">
    <form>
      <div class="col-sm-12">
        <label> Quote </label>
        <textarea v-on:keyup.enter="createNew" class="form-control" cols="200" rows="3" v-model="quote"></textarea>
        <button
          :disabled="quote.length == 0"
          class="mt-3 btn btn-primary"
          @click.prevent="createNew"
        >
          Add Quote
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data: () => ({
    quote: ''
  }),
  methods: {
    createNew() {
        this.$emit('quoteAdded', this.quote);
        this.quote = '';
    }
  }
}
</script>

<style scoped>

</style>

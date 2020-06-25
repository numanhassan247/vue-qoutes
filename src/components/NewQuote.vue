<template>
  <div class="new-quote">
    <form>
      <textarea rows="3" v-model="quote"></textarea>
      <div>
        <button @click.prevent="createNew">Add Quote</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data: () => ({
    quote: "",
  }),
  methods: {
    createNew() {
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    },
  },
};
</script>

<style></style>

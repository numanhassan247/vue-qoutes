<template>
    <div class="quote-grid">
        <app-quote v-for="(quote,i) in quotes" @click.native="deleteQuote(i)" :key="i">{{ quote }}</app-quote>
    </div>
</template>

<script>
import Quote from "./Quote.vue";
export default {
    props: ["quotes"],
    components: {
        appQuote: Quote
    },
    methods: {
        deleteQuote(i) {
            this.$emit("deleteQuote", i);
        }
    }
};
</script>

<style>
.quote-grid {
    border: green solid 1px;
    display: block;
    padding: 10px;
    margin: 10px;
}
</style>

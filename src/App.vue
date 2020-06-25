<template>
    <div id="app">
        <div class="row">
            <app-new-quote @quoteAdded="appedNewQuote"></app-new-quote>
            <app-quote-grid :quotes="quotes" @deleteQuote="deleteQuote"></app-quote-grid>
        </div>
    </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid";
import NewQuote from "./components/NewQuote";
export default {
    data: () => ({
        quotes: ["just a simple qoutes"],
        maxQuotes: 10
    }),
    components: {
        appQuoteGrid: QuoteGrid,
        appNewQuote: NewQuote
    },
    methods: {
        appedNewQuote(quote) {
            this.quotes.push(quote);
        },
        deleteQuote(i) {
            this.quotes.splice(i, 1);
        }
    }
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>

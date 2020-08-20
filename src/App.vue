<template>
    <div class="container">
        <appHeader :quoteCount="quotes.length" :maxQuotes="maxQuotes"></appHeader>
        <appQuoteGrid @quoteDeleted="deleteQuote" :quotes="quotes"></appQuoteGrid>
        <appNewQuote @quoteAdded="newQuote"></appNewQuote>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div
                    class="alert alert-warning my-3"
                    v-if="quotes.length >= maxQuotes"
                >
                    Maximum amount of quotes reached.
                </div>
                <div class="alert alert-info mt-3"> Click on a Quote to remove it </div>
            </div>
        </div>
    </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue"
import NewQuote from "./components/NewQuote.vue"
import Header from "./components/Header.vue"
    export default {
        components: { appHeader: Header, appQuoteGrid: QuoteGrid, appNewQuote: NewQuote },
        data: () => ({
            quotes: [ "Life Before Death"],
            maxQuotes: 10,
        }),
        methods: {
            newQuote(quote){
                if(this.quotes.length >= 10) {
                    alert("Maximum quotes reached.");
                    return
                } else if(quote.length == 0) {
                    alert("Quote cannot be empty.")
                    return
                }
                this.quotes.push(quote);
            },
            deleteQuote(index){
                this.quotes.splice(index, 1);
            }
        }
    }
</script>

<style>
</style>

<template>
    <div class="container">
        <appNewQuote @quoteAdded="newQuote"></appNewQuote>
        <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">
                    Info: Click on Quote to Delete
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue'
    import NewQuote from './components/NewQuote.vue'
    export default {
        data : function(){
            return {
                quotes: ['Our first quote','Our second quote'],
                maxQuotes : 10
            }
        },
        components: {
            appQuoteGrid : QuoteGrid,
            appNewQuote: NewQuote
        },
        methods : {
            newQuote(quote){
                this.quotes.push(quote);
            },
            deleteQuote(index){
                this.quotes.splice(index, 1)
            }
        }
        
    }
</script>

<style>
</style>

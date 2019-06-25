<template>
    <div class="container">
        <appHeader :quoteCount="quotes.length" :maxQuotes="maxQuotes"></appHeader>
        <appNewQuote @newQuote="addQuote"></appNewQuote>
        <appQuotesList :quotes="quotes" @quoteDeleted='deleteQuote'></appQuotesList>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info"><b>Info:</b> Click in a quote to delete it!</div>
            </div>
        </div>
    </div>
</template>

<script>
    import Header from './components/Header.vue';
    import NewQuote from './components/NewQuote.vue';
    import QuotesList from './components/QuotesList.vue';
    
    export default {
        data: function() {
            return {
                quotes: ['Just a quote of something'],
                maxQuotes: 10
            };
        },
        components: {
            appHeader: Header,
            appNewQuote: NewQuote,
            appQuotesList: QuotesList
        },
        methods: {
            addQuote(quoteText) {                
                if (this.quotes.length >= this.maxQuotes) {
                    return alert('You insert so many quotes. Please delete one');
                } 
                
                this.quotes.push(quoteText);
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);
            }
            
        }       
    }
</script>

<style>
</style>

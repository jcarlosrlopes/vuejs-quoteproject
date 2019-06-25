<template>
    <div class="row">
        <form action="">
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label>Quote</label>
                <textarea class="form-control" name="quoteText" id="quoteText" rows="3" v-model='quoteText'></textarea>        
            </div>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="addNewQuote">Add new quote</button>
            </div>
        </form>
    </div>
</template>

<script>
    // import { eventBus } from '../main';

    export default {
        data: function() {
            return {
                quoteText: ''
            }
        },
        methods: {
            addNewQuote() {
                this.$emit('newQuote', this.quoteText);
                this.quoteText = '';
            }
        }
    }
</script>

<style>

</style>


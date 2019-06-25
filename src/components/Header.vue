<template>
    <div class="row">
        <div class="col-sm-12">
            <div class="progress">
                <div class="progress-bar progress-bar-striped active" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100" :style="{ width: this.percentValue +'%' }">
                    {{ quoteCount}} / {{ maxQuotes }}
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['quoteCount', 'maxQuotes'],
    computed: {
        percentValue() {            
            return (this.quoteCount/this.maxQuotes) * 100
        } 
    }
}
</script>

<style>

</style>


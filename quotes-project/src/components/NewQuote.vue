<template>
    <div class="row">
        <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 center">
            <label for="newQuoteText">Quote</label>
            <textarea id="newQuoteText" name="newQuoteText" rows="3" class="form-control" v-on:keyup.enter.prevent="onEnter"></textarea>
        </div>
    </div>
</template>
<script>
export default {
    methods: {
        onEnter(e) {
            console.log(e.target.value);
            this.$emit('newQuoteAdded', e.target.value);
        }
    }    
}
</script>
<style>
    label {
        font: 25px bold;
        float: left;
    }
    textarea {                
        width: 200px;
        padding: 10px;
    }
    .center {
        margin: 20px auto;
    }
</style>



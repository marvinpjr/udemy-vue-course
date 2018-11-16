<template>
    <div class="row">
        <div class="col-sm-12">
            <h3>Quotes Added</h3>   
            <div class="progress">
                    <div class="progress-bar" role="progressbar" :style="widthPercentage" 
                        :aria-valuenow="(quoteCount*10).toString()" 
                        aria-valuemin="0" 
                        :aria-valuemax="(maxCount*10).toString()">
                        {{ quoteCount.toString() }} / {{ maxCount.toString() }}
                    </div>
            </div>             
        </div>       
        <!-- <progress id="quoteCounterBar" :max="maxCount.toString()" :value="quoteCount.toString()"></progress> -->
    </div>
</template>
<script>
export default {
  props: {
    quoteCount: {
      type: Number,
      default: 1
    },
    maxCount: {
      type: Number,
      default: 10
    }
  },
  computed: {
    widthPercentage: function() {
        var widthText = `${Math.round(this.quoteCount/this.maxCount*100)}%`;
        console.log(this.quoteCount)
        console.log(this.maxCount)
        console.log(widthText)
        return { width: widthText };
    }
  }
};
</script>
<style scoped>
/* progress {    
    background-color: #f3f3f3;
    border: 0;
    height: 25px;
    border-radius: 10px;
    } */
h3 {
  text-align: left;
}
</style>



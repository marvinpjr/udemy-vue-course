<template>
    <div class="row">        
       <app-quote v-for="quoteText in quotes" :key="quoteText">
         <span @click="quoteRemoved(quoteText)">{{ quoteText }} </span>          
      </app-quote>
    </div>
</template>

<script>
import Quote from "./Quote";

export default {
  props: ["quotes"],
  components: { appQuote: Quote },
  methods: {
    quoteRemoved(quoteText){
      this.$emit("quoteRemoved", quoteText);
    }
  }
};
</script>

<style scoped>
</style>



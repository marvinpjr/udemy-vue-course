<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>UserAge: {{ userAge }}</p>
    </div>
</template>

<script>
import { eventBus } from '../main'

export default {
    data: function(){
        return {
            userAge: Number
        }
    },
    created(){
        this.userAge = 40;
        eventBus.$on("ageChanged", (age) => {
            this.userAge = age;
        });
    }
}
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>

<template>
    <div class="component">
        <h3>You may edit the User here</h3>
        <p>UserAge: {{ userAge }}</p>
        <button @click="editAge">Edit Age</button>
    </div>
</template>

<script>
    import { eventBus } from '../main'
    export default {
        props: {
            userAge: Number
        },
        methods: {
            editAge() {
                this.userAge = 30;
                eventBus.$emit("ageChanged", this.userAge);
            }
        }
    }
</script>

<style scoped>
    div {
        background-color: lightgreen;
    }
</style>

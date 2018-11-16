<template>
    <div v-if="server.serverId > 0">
        <h3>Server #{{ server.serverId }}</h3>
        <div class="col">Address: {{ server.serverAddress}}</div>
        <div class="col">Status: {{ server.status}} <button @click="resetStatus()">Reboot</button></div>        
    </div>
</template>
<script>
import { eventBus } from '../../main'
export default {
    data: function() {
        return {
            server: Object
        } 
    },    
    created() {
        eventBus.$on("serverClickedEvent", (s) => 
        {
            this.server = s.clickedServer;            
        });
    },
    methods: {
        resetStatus: function(){
            this.server.status = "Normal";       
            eventBus.$emit('statusResetEvent', 
                { 
                    "resetServer": this.server
                }
            );      
        }
    }
}
</script>

<style>
</style>



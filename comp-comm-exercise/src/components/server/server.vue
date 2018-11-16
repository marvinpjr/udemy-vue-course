<template>
    <div>
        <div class="col" :class="{ 'critical': isCritical, 'atrisk': isAtRisk }">Server: {{server.serverAddress}}</div>        
        <div class="col"><button @click="serverClicked()">View Detail</button></div>
    </div>    
</template>
<script>
import { eventBus } from '../../main'
export default {
    props: {    
        server: Object
    },
    computed: {
        isCritical: function() { return this.server.status == "Critical"; },
        isAtRisk: function() { return this.server.status == "At Risk"; }                    
    },
    methods: {
        serverClicked() { 
            eventBus.$emit('serverClickedEvent', 
                { 
                    "clickedServer": this.server
                }
            ); 
        }
    }   
    // },
    // created() {
    //     eventBus.$on("statusResetEvent", (server) => {
    //         if (this.serverId == server.serverId) {
    //             this.serverStatus = server.serverStatus;
    //         }
    //     });
    // }
}
</script>
<style scoped>
    div.critical {
        color: red;
    }
    div.atrisk {
        color: orange;
    }
</style>



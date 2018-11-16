<template>
    <div class="row">
        <ul>
            <li v-for="server in servers" :key="server.serverId">
                <server :server="server"></server>
            </li>
        </ul>
    </div>
</template>
<script>

import Server from './server'
import { eventBus } from '../../main'

export default {    
    components: {
        Server
    },
    data: function() {
        return {
            "servers": [ 
                { serverId: 1, serverAddress: "10.42.7.18", status: "Critical" },
                { serverId: 2, serverAddress: "192.7.18.2", status: "Normal" },
                { serverId: 3, serverAddress: "45.75.44.12", status: "At Risk" },
            ]
        }        
    },
    created() {
        eventBus.$on("statusResetEvent", (server) => {
            var matchingServer = this.servers.find(function(s){
                return s.serverId == server.serverId;
            });
            matchingServer.status = "Normal";
        });
    }
}
</script>
<style>

</style>



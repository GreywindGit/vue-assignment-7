<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
            <app-server v-for="server in servers" :key="server.id" :server="server"></app-server>
        </ul>
    </div>
</template>

<script>
    import Server from './Server.vue';
    import { eventBus } from '../../main';

    export default {
        data: function() {
            return {
                servers: [
                    { id: 1, status: 'Normal' },
                    { id: 2, status: 'Critical' },
                    { id: 3, status: 'Unknown' },
                    { id: 4, status: 'Normal' },
                    { id: 5, status: 'Normal' }
                ]
            }
        },
        components: {
            appServer: Server
        }
    }
</script>

<style>

</style>

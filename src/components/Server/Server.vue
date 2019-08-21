<template>
  <li class="list-group-item" @click="itemClicked">Server #{{ server.id }}</li>
</template>

<script>
    import { eventBus } from '../../main';

    export default {
        props: {
            server: Object
        },
        methods: {
            itemClicked() {
                eventBus.$emit('itemClick', this.server);
            }
        }
    };
</script>

<style scoped>
</style>
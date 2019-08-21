<template>
  <div class="col-xs-12 col-sm-6">
        <h3 v-if="server">Server #{{ server.id }} status: '{{ server.status }}'</h3>
        <h3 v-else>Server status is currently not displayed.</h3>
        <button class="btn btn-primary" @click="resetStatus">Reset status</button>
  </div>
</template>

<script>
import { eventBus } from "../../main";

export default {
  data: function() {
    return {
      server: null
    };
  },
  created() {
    eventBus.$on("itemClick", data => {
      this.server = data;
    });
  },
  methods: {
      resetStatus() {
          this.server.status = 'Normal';
          eventBus.$on('resetStatus', this.server);
      }
  }
};
</script>

<style>
</style>

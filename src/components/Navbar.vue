<template>
  <b-navbar variant="dark" type="dark">
    <b-navbar-brand>
      <img :src="iconUrl" class="d-inline-block align-top" alt="">
      {{ headerText }}
    </b-navbar-brand>
    <b-navbar-nav class="ml-auto">
      <b-btn
        v-if="isAnalyticsReady"
        type="button"
        variant="outline-primary"
        size="sm"
        @click="loadNewReplay"
      >
        Load New Replay
      </b-btn>
    </b-navbar-nav>
  </b-navbar>
</template>

<script>
export default {
  computed: {
    iconUrl() {
      return this.$store.state.settings.iconUrl;
    },
    headerText() {
      return this.$store.state.settings.appName;
    },
    isAnalyticsReady() {
      return this.$store.state.settings.isAnalyticsReady;
    },
  },
  methods: {
    loadNewReplay() {
      location.reload();
    }
  }
};
</script>

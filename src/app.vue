<template>
  <div id="app" class="main-layout">
    <section class="container">
      <div class="nav sub-container">
        <div>
          <router-link class="main-logo link" to="/"> <img class="logo-image" height="45px" width="65.5" src="data:image/png;base64,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" alt=""></router-link>
        </div>
        <div>
          <router-link class="link" to="/explore">Explore</router-link> |
          <router-link class="link" to="/create">Create station</router-link> |
          <router-link class="link" to="/profile">Profile</router-link>
        </div>
      </div>
    </section>
    <section class="view-router">
      <router-view />
    </section>
    <section class="player-container">
      <playerControl />
    </section>
  </div>
</template>

<script>
import { socketService } from "./services/socket.service";
import playerControl from "./cmps/player-control";
export default {
  async created() {
    await this.$store.dispatch({ type: "loadStations" });
    socketService.setup();
  },
  components: {
    playerControl,
  },
};
</script>


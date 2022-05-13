<template>
  <div id="page-home">
    <Schedule />
    <Location />
    <Tickets />
    <Events />
    <!-- <Booths /> -->
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue"

import Title from "./home/Title.vue"
import Schedule from "./home/Schedule.vue"
import Location from "./home/Location.vue"
import Tickets from "./home/Tickets.vue"
import Events from "./events/Events.vue"
import Booths from "./booths/Booths.vue"

export default defineComponent({
  name: "Home",
  components: {
    Title,
    Schedule,
    Location,
    Tickets,
    Events,
    Booths,
  },
})
</script>

<style scoped>
#page-home {
  position: relative;
  width: 100%;
}
</style>

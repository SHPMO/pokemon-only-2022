<template>
  <div id="page-home">
    <Schedule />
    <Location />
    <Tickets />
    <Events />
    <PressPass />
    <CardSleeve />
    <Booths />
  </div>
</template>

<script setup lang="ts">
import Schedule from "./home/Schedule.vue"
import Location from "./home/Location.vue"
import Tickets from "./home/Tickets.vue"
import Events from "./events/Events.vue"
import Booths from "./booths/Booths.vue"
import PressPass from "./home/PressPass.vue"
import CardSleeve from "./home/CardSleeve.vue"
</script>

<style scoped>
#page-home {
  position: relative;
  width: 100%;
}
</style>

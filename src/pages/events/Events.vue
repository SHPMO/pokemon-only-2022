<template>
  <HomePageBase class="page-events" name="events" title="活动安排">
    <svg class="background-dash" viewBox="0 0 1920 169">
      <image x="2px" y="0px" width="1916px" height="169px" xlink:href="../../assets/background-dash/6.png" />
    </svg>
    <svg class="events-background" viewBox="0 0 1920 513">
      <image xlink:href="../../assets/page-backgrounds/events.png" x="601" y="0" height="513" width="1319" />
    </svg>
    <ul class="event-list">
      <div class="event-separator" />
      <li class="event-item">
        <div class="event-number highlighted">Activity 1</div>
        <h3>鬼火6+1</h3>
        <div class="event-details highlighted">详情待更新</div>
        <!-- <ul class="event-content">
          <li>含<span class="highlighted">入场票*1</span></li>
          <li class="highlighted">入场特典*1</li>
        </ul> -->
      </li>
      <div class="event-separator" />
      <li class="event-item">
        <div class="event-number highlighted">Activity 2</div>
        <h3>礼物交换</h3>
        <div class="event-details highlighted">详情待更新</div>
      </li>
      <div class="event-separator" />
      <li class="event-item">
        <div class="event-number highlighted">Activity 3</div>
        <h3>冻土的召唤</h3>
        <div class="event-details highlighted">详情待更新</div>
      </li>
      <div class="event-separator" />
      <li class="event-item">
        <div class="event-number highlighted">Activity 4</div>
        <h3>涂鸦墙</h3>
        <div class="event-details highlighted">详情待更新</div>
      </li>
      <div class="event-separator" />
      <li class="event-item">
        <div class="event-number highlighted">Activity 5</div>
        <h3>舞台活动</h3>
        <div class="event-details highlighted">详情待更新</div>
      </li>
      <div class="event-separator" />
    </ul>
    <!-- <div class="stage-events">
      <svg viewBox="0 0 832 228">
        <polygon points="0,57 98,0 196,57 196,171 98,228 0,171" fill="#d6c18a" />
        <text x="96px" y="0" text-anchor="middle" font-weight="bold" fill="#040404">
          <tspan x="96px" dy="4.5em" font-size="20.15px">舞台活动 1</tspan>
          <tspan x="96px" dy="1.75em" font-size="28.2px">对战</tspan>
        </text>
        <polygon points="212,57 310,0 408,57 408,171 310,228 212,171" fill="#b9685e" />
        <text x="308px" y="0" text-anchor="middle" font-weight="bold" fill="#040404">
          <tspan x="308px" dy="4.5em" font-size="20.15px">舞台活动 2</tspan>
          <tspan x="308px" dy="1.75em" font-size="28.2px">宝人三项</tspan>
        </text>
        <polygon points="424,57 522,0 620,57 620,171 522,228 424,171" fill="#6184a3" />
        <text x="520px" y="0" text-anchor="middle" font-weight="bold" fill="#040404">
          <tspan x="520px" dy="4.5em" font-size="20.15px">舞台活动 3</tspan>
          <tspan x="520px" dy="1.75em" font-size="26px">一二三、树才怪</tspan>
        </text>
        <polygon points="636,57 734,0 832,57 832,171 734,228 636,171" fill="#d6c18a" />
        <text x="732px" y="0" text-anchor="middle" font-weight="bold" fill="#040404">
          <tspan x="732px" dy="4.5em" font-size="20.15px">舞台活动 4</tspan>
          <tspan x="732px" dy="1.75em" font-size="28.2px">花牌</tspan>
        </text>
      </svg>
      <svg viewBox="0 0 620 228">
        <polygon points="0,57 98,0 196,57 196,171 98,228 0,171" fill="#a2b85d" />
        <text x="96px" y="0" text-anchor="middle" font-weight="bold" fill="#040404">
          <tspan x="96px" dy="4.5em" font-size="20.15px">舞台活动 5</tspan>
          <tspan x="96px" dy="1.5em" font-size="28.2px">拷贝不走样</tspan>
          <tspan x="96px" dy="1.2em" font-size="28.2px">古代人版！</tspan>
        </text>
        <polygon points="212,57 310,0 408,57 408,171 310,228 212,171" fill="#4d464e" />
        <text x="308px" y="0" text-anchor="middle" font-weight="bold" fill="#ffffff">
          <tspan x="308px" dy="4.5em" font-size="20.15px">舞台活动 6</tspan>
          <tspan x="308px" dy="1.5em" font-size="28.2px">宝可梦</tspan>
          <tspan x="308px" dy="1.2em" font-size="28.2px">大量发生</tspan>
        </text>
        <polygon points="424,57 522,0 620,57 620,171 522,228 424,171" fill="#e0af50" />
        <text x="520px" y="0" text-anchor="middle" font-weight="bold" fill="#040404">
          <tspan x="520px" dy="4.5em" font-size="20.15px">舞台活动 7</tspan>
          <tspan x="520px" dy="1.5em" font-size="28.2px">望罗先生</tspan>
          <tspan x="520px" dy="1.2em" font-size="28.2px">不要脸</tspan>
        </text>
      </svg>
    </div> -->
  </HomePageBase>
</template>

<script lang="ts">
import { defineComponent } from "vue"
import HomePageBase from "../../components/HomePageBase.vue"

export default defineComponent({
  name: "Events",
  components: {
    HomePageBase,
  },
})
</script>

<style scoped>
.page-events {
  margin-top: 172px;
}

.background-dash {
  margin-top: -272px;
}


.events-background {
  margin-left: auto;
  margin-right: auto;
  width: 100%;
  height: auto;
  z-index: 0;
  text-align: center;
}

.event-list {
  list-style: none;
  display: flex;
  align-items: start;
  flex-wrap: wrap;
}

.event-item {
  width: 280px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.event-separator {
  position: relative;
  width: 3px;
  height: 330px;
  border-radius: 50%;
  background-color: #18171b;
}

.highlighted {
  color: #d31751;
}

.event-item:nth-child(4n) .highlighted {
  color: #0f65fd;
}

.event-number {
  margin-top: 38px;
  text-transform: uppercase;
  font-size: 15px;
  font-weight: bold;
}

.event-item>h3 {
  font-size: 28px;
  margin: 0;
}

.event-details {
  margin-top: 4px;
  font-size: 20px;
  font-weight: bold;
}

.event-content {
  margin-top: 28px;
  height: 116px;
  padding: 0;
  list-style: none;
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: 15px;
  font-weight: bold;
}

.event-help-text {
  text-align: center;
  font-size: 10px;
}

.stage-events {
  width: 76.46%;
  min-width: 720px;
  height: auto;
  z-index: 0;
  display: flex;
  font-family: "Noto Serif SC", serif;
  flex-wrap: wrap;
}

.stage-events>svg:nth-child(1) {
  width: 56.676%;
}

.stage-events>svg:nth-child(2) {
  width: 42.234%;
  margin-left: 1.09%;
}

@media only screen and (max-width: 1024px) {
  .stage-events {
    min-width: 350px;
  }

  .stage-events>svg:nth-child(1) {
    width: 100%;
    margin: auto;
  }

  .stage-events>svg:nth-child(2) {
    width: 74.518%;
    margin: auto;
    margin-top: -24px;
  }
}
</style>

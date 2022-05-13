<template>
  <HomePageBase class="page-schedule" name="schedule" title="当日行程">
    <svg class="background-dash" viewBox="0 0 1920 982">
      <image
        x="4px"
        y="62px"
        width="1916px"
        height="169px"
        xlink:href="../../assets/background-dash/1.png"
      />
      <image
        x="1789px"
        y="0px"
        width="131px"
        height="982px"
        xlink:href="../../assets/background-dash/2.png"
      />
    </svg>
    <svg class="schedule-content" viewBox="0 0 1920 755">
      <image
        xlink:href="../../assets/page-backgrounds/schedule.png"
        x="4"
        y="80"
        height="405"
        width="1561"
      />
      <polygon
        points="1173,543 1295.1095819336058,472.5 1417.2191638672116,543.0 1417.2191638672116,684.0 1295.1095819336058,754.5 1173.0,684"
        fill="#e0af50"
      />
      <text
        font-size="35px"
        x="1295.11px"
        y="472.5px"
        text-anchor="middle"
        font-weight="bold"
        fill="#040404"
      >
        <tspan x="1295.11px" dy="3.5em">16:30</tspan>
        <tspan x="1295.11px" dy="1.75em">闭场</tspan>
      </text>
      <polygon
        points="897,543 1019.1095819336058,472.5 1141.2191638672116,543.0 1141.2191638672116,684.0 1019.1095819336058,754.5 897.0,684"
        fill="#4d464e"
      />
      <text
        font-size="35px"
        x="1019.11px"
        y="472.5px"
        text-anchor="middle"
        font-weight="bold"
        fill="#FFFFFF"
      >
        <tspan x="1019.11px" dy="3.5em">15:30</tspan>
        <tspan x="1019.11px" dy="1.75em">抽奖活动</tspan>
      </text>
      <polygon
        points="621,543 743.1095819336058,472.5 865.2191638672116,543.0 865.2191638672116,684.0 743.1095819336058,754.5 621.0,684"
        fill="#a2b85d"
      />
      <text
        font-size="35px"
        x="743.11px"
        y="472.5px"
        text-anchor="middle"
        font-weight="bold"
        fill="#040404"
      >
        <tspan dy="3em">11:30</tspan>
        <tspan x="743.11px" dy="1.75em">舞台活动</tspan>
        <tspan x="743.11px" dy="1.2em">表演开始</tspan>
      </text>
      <polygon
        points="345,543 467.10958193360585,472.5 589.2191638672117,543.0 589.2191638672117,684.0 467.10958193360585,754.5 345.0,684.0"
        fill="#b9685e"
      />
      <text
        font-size="35px"
        x="467.11px"
        y="472.5px"
        text-anchor="middle"
        fill="#FFFFFF"
      >
        <tspan font-weight="bold" x="467.11px" fill="#040404" dy="3em">
          10:30
        </tspan>
        <tspan font-weight="bold" x="467.11px" fill="#040404" dy="1.3em">
          舞台预告
        </tspan>
        <tspan font-size="15px" x="467.11px" dy="2.4em">广播提醒</tspan>
        <tspan font-size="15px" x="467.11px" dy="1.2em">
          还有一个小时舞台开始
        </tspan>
        <tspan font-size="15px" x="467.11px" dy="1.2em">推荐大家去吃饭x</tspan>
      </text>
      <polygon
        points="1313,315 1435.1095819336058,244.5 1557.2191638672116,315 1557.2191638672116,456 1435.1095819336058,526.5 1313,456"
        fill="#6184a3"
      />
      <text
        font-size="35px"
        x="1435.11px"
        y="244.5px"
        text-anchor="middle"
        font-weight="bold"
        fill="#040404"
      >
        <tspan x="1435.11px" dy="3.5em">10:30</tspan>
        <tspan x="1435.11px" dy="1.75em">战斗区开始</tspan>
      </text>
      <polygon
        points="1037,315 1159.1095819336058,244.5 1281.2191638672116,315 1281.2191638672116,456 1159.1095819336058,526.5 1037,456"
        fill="#b9685e"
      />
      <text
        font-size="35px"
        x="1159.11px"
        y="244.5px"
        text-anchor="middle"
        font-weight="bold"
        fill="#040404"
      >
        <tspan x="1159.11px" dy="3em">9:30</tspan>
        <tspan x="1159.11px" dy="1.75em">开场</tspan>
        <tspan font-size="20px" font-weight="normal" x="1159.11px" dy="1.5em">
          10:30 前不可出场
        </tspan>
      </text>
      <polygon
        points="485,315 607.1095819336058,244.5 729.2191638672116,315.0 729.2191638672116,456.0 607.1095819336058,526.5 485,456"
        fill="#d6c18a"
      />
      <text
        font-size="35px"
        x="607.11px"
        y="244.5px"
        text-anchor="middle"
        font-weight="bold"
        fill="#040404"
      >
        <tspan x="607.11px" dy="3.5em">8:00</tspan>
        <tspan x="607.11px" dy="1.75em">摊主入场</tspan>
      </text>
    </svg>

    <!-- <div class="schedule-list">
    </div> -->
  </HomePageBase>
</template>

<script lang="ts">
import { defineComponent } from "vue"

import HomePageBase from "../../components/HomePageBase.vue"
import ItemCard from "../../components/ItemCard.vue"

export default defineComponent({
  name: "Schedule",
  components: {
    HomePageBase,
    ItemCard,
  },
})
</script>

<style scoped>
.page-schedule {
  margin-top: 32px;
}

.background-dash {
  margin-top: -32px;
}

.schedule-content {
  margin-top: 80px;
  width: 100%;
  min-width: 720px;
  height: auto;
  z-index: 0;
  font-family: "Noto Serif SC", serif;
}
</style>

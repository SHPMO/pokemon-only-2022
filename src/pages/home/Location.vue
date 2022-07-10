<template>
  <HomePageBase class="page-location" name="location" title="场地信息">
    <svg class="background-dash" viewBox="0 0 1920 811">
      <image x="0px" y="64px" width="1920px" height="317px" xlink:href="../../assets/background-dash/3.png" />
      <image xlink:href="../../assets/page-backgrounds/location.png" x="0" y="0" width="1920px" height="700px" />
    </svg>
    <div class="location-container">
      <svg class="location-content" viewBox="0 0 1477 1080">
        <image class="map-container" xlink:href="../../assets/location/map-container.png" x="0" y="392" height="633"
          width="1477" />
        <a class="map" href="https://j.map.baidu.com/4e/gek" target="_blank">
          <image xlink:href="../../assets/location/map.png" x="301" y="456.5" height="504.38179425511194" width="875" />
        </a>
        <text class="help-text" fill="#ffffff" x="1160" y="980" font-size="13px" text-anchor="end">
          *来源百度地图
        </text>
      </svg>
    </div>
    <div class="location-text">
      漕宝路 1688 号诺宝中心 | 9 号线星中路 2 号口
    </div>
  </HomePageBase>
</template>

<script lang="ts">
import HomePageBase from "../../components/HomePageBase.vue"

export default {
  name: "Location",
  components: {
    HomePageBase,
  },
}
</script>

<style scoped>
.page-location {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 32px;
}

.background-dash {
  margin-top: -96px;
}

.location-container {
  margin-top: 80px;
  margin-left: auto;
  margin-right: auto;
  width: 76.93%;
  min-width: 720px;
  z-index: 1;
}

.location-content {
  width: 100%;
  height: auto;
  z-index: 0;
}

.location-text {
  color: #ffffff;
  background-color: #21222c;
  font-weight: bold;
  border-radius: 10px;
  font-size: 24px;
  padding: 8px 20px;
}

@media only screen and (max-width: 768px) {

  .location-text {
    font-size: 20px;
  }

  .map-container {
    display: none;
  }
}

@media only screen and (max-width: 600px) {
  .location-text {
    font-size: 12px;
  }

  .location-container {
    min-width: unset;
    overflow-x: hidden;
  }

  .location-content {
    margin-top: -50px;
    margin-left: -88px;
    width: 480px;
  }
}
</style>

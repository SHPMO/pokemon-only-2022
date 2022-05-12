<template>
  <HomePageBase class="page-location" name="location" title="场地信息">
    <svg class="location-content" viewBox="0 0 1477 1080">
      <image
        xlink:href="../../assets/page-backgrounds/location.png"
        x="280.5"
        y="56"
        height="465"
        width="755"
      />
      <image
        xlink:href="../../assets/location/map-container.png"
        x="0"
        y="392"
        height="633"
        width="1477"
      />
      <a class="map" href="https://j.map.baidu.com/4e/gek" target="_blank">
        <image
          xlink:href="../../assets/location/map.png"
          x="301"
          y="456.5"
          height="504.38179425511194"
          width="875"
        />
      </a>
      <text
        class="help-text"
        fill="#ffffff"
        x="1160"
        y="980"
        font-size="13px"
        text-anchor="end"
      >
        *来源百度地图
      </text>
    </svg>
    <div class="location-text">
      漕宝路 1688 号诺宝中心 | 9 号线星中路 2 号口
    </div>
  </HomePageBase>
</template>

<script>
import HomePageBase from "../../components/HomePageBase.vue"
import ItemCard from "../../components/ItemCard.vue"

export default {
  name: "Location",
  components: {
    ItemCard,
    HomePageBase,
  },
}
</script>

<style scoped>
.page-location {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.location-content {
  margin-top: 80px;
  margin-left: auto;
  margin-right: auto;
  width: 76.93%;
  min-width: 720px;
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

@media only screen and (max-width: 600px) {
  .map-container {
    background: none;
    width: 90%;
    padding-top: 0;
  }

  .map {
    position: relative;
    top: 0;
    left: 0;
    width: 100%;
  }

  .helpText {
    position: relative;
    left: 0;
    bottom: 0;
    width: 100%;
    color: #040000;
  }
}
</style>
<style>
@media only screen and (max-width: 768px) {
  .info > .item-card > div {
    width: 354px;
  }
}
</style>

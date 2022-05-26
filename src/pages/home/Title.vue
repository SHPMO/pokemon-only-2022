<template>
  <div v-if="show" class="home-title">
    <div class="background" />
    <div class="content">
      <div class="time-place">
        <div class="time-place-background" />
        <svg class="time-place-text" viewBox="0 0 823 518">
          <text kerning="auto" font-size="20px" x="216px" y="393.156px">
            <tspan font-size="20px" font-family="Noto Sans SC" font-weight="bold" fill="#030000">
              &#28437;&#23453;&#36335;&#49;&#54;&#56;&#56;&#21495;&#35834;&#23453;&#20013;&#24515;&#32;&#32;|&#32;&#32;&#57;&#21495;&#32447;&#26143;&#20013;&#36335;&#50;&#21495;&#21475;
            </tspan>
          </text>
          <text kerning="auto" font-size="24px" x="236px" y="149.928px">
            <tspan font-size="24px" font-weight="bold" fill="#030000">
              SHANGHAI&#32;POKEMON&#32;ONLY
            </tspan>
          </text>
          <text kerning="auto" font-size="24px" x="383px" y="117.928px">
            <tspan font-size="24px" font-weight="bold" fill="#030000">
              &#50;&#48;&#50;&#50;
            </tspan>
          </text>
        </svg>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed } from '@vue/reactivity'
import { useRoute } from 'vue-router'

const route = useRoute()
const show = computed(() => {
  const path = route.path
  return !path.startsWith('/booths') && !path.startsWith('/items')
})
</script>

<style scoped>
.home-title {
  width: 100%;
  user-select: none;
  position: relative;
  padding-left: 56px;
  padding-right: 56px;
}

.background {
  width: 100%;
  max-width: 1806px;
  margin-left: auto;
  margin-right: auto;
  padding-top: 56.25%;
  background-image: url("../../assets/title/background.png");
  background-position: top right;
  background-size: 100% auto;
  background-repeat: no-repeat;
}

.content {
  position: relative;
  width: 100%;
  display: flex;
  flex-direction: column-reverse;
}

.time-place {
  position: relative;
  width: 42.86%;
  min-width: 370px;
  height: auto;
  /* margin: auto;
  margin-bottom: -8%; */
  margin-left: auto;
  margin-right: auto;
  margin-top: -13.49%;
}

.time-place-background {
  width: 100%;
  background: url("../../assets/title/time-place-background.png") no-repeat;
  background-size: contain;
  padding-top: 62.94%;
}

.time-place-text {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

@media only screen and (max-width: 1024px) {
  .home-title {
    padding-left: 24px;
    padding-right: 24px;
  }
}

@media only screen and (max-width: 768px) {
  .home-title {
    padding-left: 4px;
    padding-right: 4px;
  }
}
</style>

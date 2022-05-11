<template>
  <div class="home-title">
    <div class="background" />
    <div class="content">
      <div class="time-place">
        <div class="time-place-background" />
        <svg class="time-place-text" viewBox="0 0 823 518">
          <text kerning="auto" font-size="20px" x="216px" y="393.156px">
            <tspan
              font-size="20px"
              font-family="Noto Sans SC"
              font-weight="bold"
              fill="#030000"
            >
              &#28437;&#23453;&#36335;&#49;&#54;&#56;&#56;&#21495;&#35834;&#23453;&#20013;&#24515;&#32;&#32;|&#32;&#32;&#57;&#21495;&#32447;&#26143;&#20013;&#36335;&#50;&#21495;&#21475;
            </tspan>
          </text>
          <text kerning="auto" font-size="24px" x="236px" y="149.928px">
            <tspan
              font-size="24px"
             
              font-weight="bold"
              fill="#030000"
            >
              SHANGHAI&#32;POKEMON&#32;ONLY
            </tspan>
          </text>
          <text kerning="auto" font-size="24px" x="383px" y="117.928px">
            <tspan
              font-size="24px"
             
              font-weight="bold"
              fill="#030000"
            >
              &#50;&#48;&#50;&#50;
            </tspan>
          </text>
        </svg>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Title",
  components: {},
});
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
  /* position: absolute; */
  position: relative;
  width: 100%;
  /* height: 100%; */
  /* top: 0; */
  /* left: 0; */
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

@media only screen and (orientation: landscape) and (min-width: 601px) {
  /* .background {
    height: 100vh;
    padding-top: 0;
    background-size: auto 100%;
  } */

  @media (max-width: 1280px) {
  }
}

@media only screen and (orientation: portrait),
  only screen and (max-width: 600px) {
  .background {
    position: relative;
    background-size: 105% auto;
    background-image: linear-gradient(
        to bottom,
        rgba(248, 248, 248, 0) 72.1%,
        rgba(248, 248, 248, 1)
      ),
      url("../../assets/title/background.png");
  }

  .home-title {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .content {
    position: relative;
    width: 80%;
    padding-top: 22.794%;
    margin-top: -5%;
  }

  .slogan {
    width: 50%;
    min-width: 50%;
    top: 30%;
    left: 51.5%;
  }

  .address {
    width: 100%;
    min-width: 100%;
    top: 0;
    left: 0;
  }
}

/* @media only screen and (max-width: 600px) {
} */
</style>

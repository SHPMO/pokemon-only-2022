<template>
  <Header />
  <div class="back-to-top" :class="{ fullHeight: inFooter }">
    <div :class="{ inTitle, inFooter }" @click="backToTop">
      <div>回到<br />上方</div>
    </div>
  </div>
  <router-view />
  <Footer />
</template>

<script lang="ts">
import { defineComponent } from "vue"

import Header from "./components/Header.vue"
import Footer from "./components/Footer.vue"

import { inHome, isLandscapeOrientation, setHash, setTitle } from "./utils/view"

export default defineComponent({
  name: "App",
  components: {
    Header,
    Footer,
  },
  data() {
    return {
      inTitle: true,
      inFooter: false,
      previousTop: -1,
    }
  },
  methods: {
    backToTop() {
      setHash("", true) // , false)
    },
    onScroll() {
      const currentTop =
        window.pageYOffset || document.documentElement.scrollTop
      this.inTitle =
        currentTop <=
        (isLandscapeOrientation() ? 410 : 131) + window.innerHeight * 0.1
      this.inFooter =
        document.documentElement.scrollHeight -
          currentTop -
          window.innerHeight * 0.9 +42 <
        196
      console.log([document.documentElement.scrollHeight, currentTop, window.innerHeight])

      const goingDown = currentTop > this.previousTop
      this.previousTop = currentTop
      let t = window.innerHeight / 3
      if (!goingDown && (isLandscapeOrientation() || currentTop > t)) {
        t *= 2
      }
      if (inHome()) {
        const anchors = Array.from(
          document.querySelectorAll(".home-page > .anchor")
        ).reverse()
        for (const anchor of anchors) {
          if (anchor?.getBoundingClientRect().top <= t) {
            const name = anchor.getAttribute("name")
            setHash(name)
            setTitle(anchor.getAttribute("title"))
            return
          }
        }
        setHash("")
        setTitle("首页")
      }
    },
  },
  mounted() {
    window.addEventListener("scroll", this.onScroll)
    setHash(location.hash.slice(1), true, false)
    this.onScroll()
  },
  unmounted() {
    window.removeEventListener("scroll", this.onScroll)
  },
})
</script>

<style scoped>
.back-to-top {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
}

.fullHeight {
  height: 100%;
}

.back-to-top > div {
  position: fixed;
  right: 10%;
  bottom: 10%;
  cursor: pointer;
  background-image: url("./assets/home/top.png");
  width: 125px;
  height: 124px;
  background-repeat: no-repeat;
  display: flex;
  z-index: 2;
}

.back-to-top > div > div {
  margin: auto;
  color: #d6c18a;
  text-align: center;
  font-size: 25px;
  line-height: 28px;
  letter-spacing: 2px;
}

.back-to-top > div.inTitle {
  position: absolute;
  bottom: -390px;
}

.back-to-top > div.inFooter {
  position: absolute;
  bottom: 134px;
}

@media only screen and (orientation: portrait) {
  .back-to-top > div.inTitle {
    position: absolute;
    bottom: -131px;
  }
}

@media only screen and (max-width: 600px) {
  .back-to-top {
    display: none;
  }
}
</style>

<style>
*,
::before,
::after {
  box-sizing: border-box;
}

@font-face {
  font-family: "nevis";
  src: local("nevis"), url("./assets/fonts/nevis.ttf");
  font-weight: normal;
}

@font-face {
  font-family: "Noto Sans SC";
  src: local("Noto Sans SC"), url("./assets/fonts/NotoSansHans-Regular.otf");
  font-weight: normal;
}

@font-face {
  font-family: "Noto Sans SC";
  src: local("Noto Sans SC"), url("./assets/fonts/NotoSansHans-DemiLight.otf");
  font-weight: lighter;
}

@font-face {
  font-family: "Noto Sans SC";
  src: local("Noto Sans SC"), url("./assets/fonts/NotoSansHans-Bold.otf");
  font-weight: bold;
}

html,
body {
  margin: 0;
  width: 100%;
  color: #030000;
  background: #ffffff;
  font-family: "nevis", "Noto Sans SC", sans-serif;
}

a {
  text-decoration: none;
  color: #030000;
}

a:hover {
  color: #3999d6;
}

#app-pmo2022 {
  position: relative;
  width: 100%;
}

.hide {
  display: none !important;
}

.blue {
  color: #3999d6;
}

.red {
  color: #d31751;
}

.gray {
  color: #808080;
}
</style>

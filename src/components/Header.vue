<template>
  <header class="header">
    <div class="header-content">
      <router-link to="/#">
        <img class="logo" src="../assets/common/logo.png" alt="" />
      </router-link>
      <nav class="navs">
        <ul>
          <li class="nav">
            <Anchor target="schedule">
              <div class="nav-ja">
                <span>スケジュール</span>
              </div>
              <span class="nav-zh">当日行程</span>
            </Anchor>
          </li>
          <div class="nav-separator" />
          <li class="nav">
            <Anchor target="location">
              <div class="nav-ja">
                <span>活動場所</span>
              </div>
              <span class="nav-zh">场地信息</span>
            </Anchor>
          </li>
          <div class="nav-separator" />
          <li class="nav">
            <Anchor target="tickets">
              <div class="nav-ja">
                <span>入場券</span>
              </div>
              <span class="nav-zh">票务信息</span>
            </Anchor>
          </li>
          <div class="nav-separator" />
          <li class="nav">
            <Anchor target="events">
              <div class="nav-ja">
                <span>アクティブプロセス</span>
              </div>
              <span class="nav-zh">活动安排</span>
            </Anchor>
          </li>
          <div class="nav-separator" />
          <li class="nav">
            <Anchor target="booths">
              <div class="nav-ja">
                <span>ブース</span>
              </div>
              <span class="nav-zh">现场摊位</span>
            </Anchor>
          </li>
          <div class="nav-separator" />
        </ul>
      </nav>
    </div>
  </header>
</template>

<script lang="ts">
import { defineComponent } from "vue"

import Anchor from "./Anchor.vue"

export default defineComponent({
  name: "Header",
  components: {
    Anchor,
  },
})
</script>

<style scoped>
.header {
  position: relative;
  width: 100%;
  height: 303px;
  background: #ffffff;
  z-index: 1;
  padding: 56px;
}

.header-content {
  margin-left: auto;
  margin-right: auto;
  max-width: 1810px;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  overflow: hidden;
}

.logo {
  position: relative;
  width: auto;
  height: 100%;
}

.navs {
  flex: 1 1 auto;
}

.navs>ul {
  display: flex;
  height: 100%;
  list-style: none;
  padding: 0;
  margin: 0;
  justify-content: flex-end;
  align-items: center;
}

.nav {
  position: relative;
  display: flex;
  max-width: 312px;
  height: 100%;
  flex: 1 1 auto;
}

.nav-separator {
  position: relative;
  width: 3px;
  height: 62px;
  border-radius: 50%;
  background-color: #18171b;
}

.nav:hover::before {
  content: "";
  position: absolute;
  background: url("../assets/header/nav-hover.png") no-repeat center center;
  background-size: contain;
  width: 200%;
  height: 300%;
  top: -100%;
  left: -58%;
  z-index: -1;
}

.nav-ja {
  color: #d31751;
  font-size: 14px;
  letter-spacing: 1px;
  font-weight: bold;
  line-height: 1.2rem;
  width: 0;
  height: 1.2rem;
  overflow: visible;
  white-space: nowrap;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.nav-ja>span {
  display: block;
}

.nav-zh {
  color: #151317;
  font-size: 28px;
  font-weight: bold;
  line-height: 2rem;
}

@media only screen and (max-width: 1280px) {
  .header {
    padding: 24px;
  }

  .nav:hover::before {
    display: none;
  }

  .nav-ja {
    font-size: 12px;
    line-height: 1rem;
    height: 1rem;
  }

  .nav-zh {
    font-size: 20px;
    line-height: 1.5rem;
  }
}

@media only screen and (max-width: 768px) {
  .header {
    padding: 24px;
  }

  .header-content {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .logo {
    width: 100%;
    height: auto;
  }

  .navs {
    margin-top: 8px;
    width: 100%;
  }
}

@media only screen and (max-width: 600px) {
  .nav-ja {
    margin-top: 16px;
    font-size: 8px;
    line-height: 8px;
    height: 8px;
  }

  .nav-zh {
    font-size: 12px;
    line-height: 1rem;
  }
}
</style>

<style>
.nav>a {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-left: auto;
  margin-right: auto;
}

.nav>a>span {
  display: block;
  text-align: center;
  text-transform: uppercase;
}
</style>
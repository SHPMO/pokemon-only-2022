<template>
  <div class="home-page">
    <a class="anchor" :name="name" :title="title" />
    <div class="title-container">
      <div class="title">
        <h2>{{ title }}</h2>
      </div>
      <slot name="title" />
    </div>
    <div class="content">
      <slot />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue"
import { inHome, setTitle } from "../utils/view"

export default defineComponent({
  name: "HomePageBase",
  props: {
    name: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
  },
  mounted() {
    if (!inHome()) {
      setTitle(this.title)
    }
  },
})
</script>

<style scoped>
.home-page {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  min-height: 100vh;
}

.home-page::after {
  content: "";
  margin-bottom: 50px;
}

.anchor {
  position: absolute;
  user-select: none;
  top: 0;
  opacity: 0;
}

.title-container {
  position: absolute;
  width: 100%;
  top: 0;
  left: 0;
  height: auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.title {
  user-select: none;
  margin-top: 9.259vh;
  width: 112px;
  height: 315px;
  background: url("../assets/common/page-title-background.png") no-repeat;
  background-size: contain;
  display: flex;
  z-index: 1;
}

.title > h2 {
  font-size: 48px;
  width: 48px;
  line-height: 60px;
  color: #040000;
  font-family: 'Noto Serif SC', serif;
  font-weight: 900;
  margin: auto;
}

.content {
  width: 100%;
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}

@media only screen and (max-width: 1280px) {
  .title {
    width: 80px;
    height: 225px;
  }

  .title > h2 {
    width: 30px;
    font-size: 30px;
    line-height: 37.5px;
  }
}

@media only screen and (max-width: 768px) {
  .home-page {
    min-height: unset;
  }

  .title {
    width: 56px;
    height: 157px;
    margin-top: 0;
  }

  .title > h2 {
    width: 24px;
    font-size: 24px;
    line-height: 30px;
  }

  .zeros {
    letter-spacing: 4px;
    font-size: 9px;
    margin-top: -4px;
  }

  .home-page::after {
    margin-bottom: 28px;
  }
}
</style>

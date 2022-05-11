<template>
  <div class="home-page">
    <a class="anchor" :name="name" :title="title" />
    <div class="title">
      <h2>{{ title }}</h2>
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
  }
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
  margin-bottom: 100px;
}

.anchor {
  position: absolute;
  user-select: none;
  top: 0;
  opacity: 0;
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
  font-weight: bold;
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
    max-width: 400px;
  }

  h1 {
    font-size: 63px;
  }

  h2 {
    font-size: 30px;
    margin-top: -15px;
  }

  .zeros {
    letter-spacing: 6px;
    font-size: 12px;
    margin-top: -5px;
  }
}

@media only screen and (max-width: 768px) {
  .home-page {
    min-height: unset;
  }

  .title {
    width: auto;
    margin-top: 5vh;
  }

  h1 {
    font-size: 50px;
  }

  h2 {
    font-size: 24px;
    margin-top: -12px;
  }

  .zeros {
    letter-spacing: 4px;
    font-size: 9px;
    margin-top: -4px;
  }

  .home-page::after {
    margin-bottom: 64px;
  }
}
</style>

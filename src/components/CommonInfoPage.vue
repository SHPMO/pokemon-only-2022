<template>
  <HomePageBase class="page-common" :name="name" :title="title">
    <slot name="background" class="background-dash"></slot>
    <h2 class="common-title">{{ title2 }}</h2>
    <div class="common-container">
      <slot></slot>
    </div>
  </HomePageBase>
</template>

<script setup lang="ts">
import HomePageBase from "./HomePageBase.vue"

defineProps<{
  name: string
  title: string
  title2: string
}>()
</script>

<style>
.page-common {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.background-dash {
  margin-top: -96px;
}

.common-title {
  z-index: 1;
  margin-top: 440px;
  font-size: 2rem;
}

.common-container {
  z-index: 1;
  font-size: 1.25rem;
  font-weight: bold;
  line-height: 2rem;
  text-align: left;
  width: 76.93%;
  max-width: 1200px;
  min-width: 720px;
}

.common-container > .small-header {
  margin-top: 3rem;
  margin-bottom: 1rem;
}

.common-container > ul {
  list-style: none;
  padding-inline-start: 0;
}

.common-container > ul > li::before {
  content: "◆";
  color: #d6c18a;
  display: inline-block;
  width: 2rem;
}

.common-container > p {
  margin: 0;
  text-indent: 2rem;
}

.common-container > figure {
  text-align: center;
}

.common-container > figure > img {
  width: 75%;
  height: auto;
}

@media only screen and (max-width: 1024px) {
  .background-dash {
    margin-top: -48px;
  }
  .common-title {
    margin-top: 220px;
    font-size: 1.5rem;
  }
  .common-container {
    font-size: 1rem;
  }
}

@media only screen and (max-width: 600px) {
  .background-dash {
    margin-top: 0;
  }

  .common-title {
    margin-top: 200px;
    font-size: 1rem;
  }

  .common-container {
    min-width: unset;
    font-size: 0.75rem;
  }

  .common-container > figure > img {
    width: 100%;
  }
}
</style>

<template>
  <div class="pmo-separator" :class="vertical ? 'separator-vertical' : 'separator-horizontal'">
    <div class="separator" />
    <img src="../assets/common/icon-flower.png" />
    <div class="separator" />
  </div>
</template>

<script setup lang="ts">
defineProps<{ vertical?: boolean }>()
</script>

<style>
.pmo-separator {
  display: flex;
  align-items: center;
}

.pmo-separator>.separator {
  margin: auto;
  border: dashed 2px #d6c18a;
}

.separator-vertical {
  height: 100%;
  max-height: 1440px;
  width: 44px;
  margin: auto 4px;
  flex-direction: column;
}

.separator-vertical>.separator {
  height: 40%;
  width: 4px;
}

.separator-horizontal {
  width: 100%;
  max-width: 1440px;
  height: 41px;
  margin: 4px auto;
  flex-direction: row;
}

.separator-horizontal>.separator {
  width: 40%;
  height: 4px;
}
</style>

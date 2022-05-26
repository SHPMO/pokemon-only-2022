<template>
  <div class="booth-card" :class="`booth-${color || 'red'}`">
    <div class="booth-number">
      <div>
        {{ booth.seller_id || '--' }}
      </div>
    </div>
    <div class="booth-booth">booth</div>
    <router-link class="booth-name serif" :to="`/booths/${booth.id}`">
      {{ booth.circle_name }}
    </router-link>
    <router-link class="booth-image" :to="`/booths/${booth.id}`">
      <ImageView :src="booth.circle_image" disabled />
    </router-link>
  </div>
</template>

<script setup lang="ts">
import { Seller } from '../utils/models'
import ImageView from './ImageView.vue'

defineProps<{
  booth: Seller
  color?: 'red' | 'blue' | undefined
}>()
</script>

<style scoped>
.booth-card {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.booth-number {
  color: #fff;
  width: 125px;
  height: 142px;
  background-size: contain;
  background-repeat: no-repeat;
  display: flex;
  align-items: center;
}

.booth-number>div {
  font-size: 2rem;
  margin: auto;
  margin-top: 3.6rem;
}

.booth-red .booth-number {
  background-image: url("../assets/booths/booth-red.png");
}

.booth-blue .booth-number {
  background-image: url("../assets/booths/booth-blue.png");
}

.booth-booth {
  text-transform: uppercase;
  margin-top: 8px;
}

.booth-name {
  font-size: 1.75rem;
  font-weight: bold;
}

.booth-red .booth-name:hover {
  color: #d31751;
}

.booth-image {
  display: flex;
  width: 360px;
  height: 360px;
  margin-top: 8px;
}
</style>

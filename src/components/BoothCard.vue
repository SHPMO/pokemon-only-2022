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
  min-width: 300px;
}

.booth-number {
  color: #fff;
  width: 125px;
  height: 142px;
  background-size: contain;
  background-repeat: no-repeat;
  display: flex;
  align-items: center;
  user-select: none;
}

.booth-number>div {
  font-size: 2rem;
  margin: auto;
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
  text-align: center;
}

.booth-red .booth-name:hover {
  color: #d31751;
}

.booth-image {
  display: flex;
  width: 100%;
  padding-top: 100%;
  position: relative;
  margin-top: 8px;
}

@media only screen and (max-width: 768px) {
  .booth-card {
    min-width: 250px;
  }
}
@media only screen and (max-width: 600px) {
  .booth-card {
    min-width: 150px;
  }
}
</style>

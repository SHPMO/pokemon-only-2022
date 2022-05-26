<template>
  <BoothPageBase type="booth" :page="page" :max-page="maxPage" :update-page="updatePage">
    <div v-if="booth === null" class="booth-null">
      无此摊位。
    </div>
    <div v-else class="booth-page">
      <div class="booth-info">
        <BoothCard :booth="booth" :color="booth.seller_id.startsWith('A') ? 'red' : 'blue'">
          {{ booth.circle_name }}
        </BoothCard>
        <div class="booth-description">
          {{ booth.circle_description }}
        </div>
      </div>
      <PMOSeparator />
      <div class="items-header">商品列表</div>
      <ItemList :update-states="updateStates" :sellerID="booth.id" />
    </div>
  </BoothPageBase>
</template>

<script lang="ts">
import { defineComponent } from "vue"

import BoothPageBase from "./BoothPageBase.vue"
import ItemList from "./ItemList.vue"

import { getSeller, Seller } from "../../utils/models"
import { getQueryPage, setTitle } from "../../utils/view"
import ImageView from "../../components/ImageView.vue"
import BoothCard from "../../components/BoothCard.vue"
import PMOSeparator from "../../components/PMOSeparator.vue"

export default defineComponent({
  name: "BoothPage",
  components: {
    ImageView,
    BoothPageBase,
    ItemList,
    BoothCard,
    PMOSeparator
  },
  methods: {
    updatePage(page: number) {
      if (isNaN(page) || page < 1 || page > this.maxPage) {
        page = 1
      }
      this.page = page
      if (this.updatePageState !== undefined) {
        this.updatePageState(page)
      }
    },
    updateStates(maxPage: number, updatePage: (page: number) => void) {
      this.maxPage = maxPage
      this.updatePageState = updatePage
      const page = getQueryPage(this.$route, this.maxPage)
      this.updatePage(page)
    }
  },
  data() {
    return {
      booth: null as Seller | null,
      page: 0,
      maxPage: 0,
      updatePageState: undefined as undefined | ((page: number) => void)
    }
  },
  async mounted() {
    const id = parseInt(this.$route.params.id as string)
    this.booth = await getSeller(id)
    if (this.booth != null) {
      setTitle(`${this.booth.circle_name} - 现场摊位`)
    }
  }
})
</script>

<style scoped>
.booth-null {
  margin: 80px auto auto;
  font-size: 2rem;
}

.booth-page {
  width: 100%;
}

.items-header {
  font-weight: bold;
  font-size: 2.5rem;
  margin-top: 1rem;
}

.booth-info {
  max-width: 560px;
  display: flex;
  flex-direction: column;
  margin: 16px auto auto;
  justify-content: center;
}

.booth-image {
  display: flex;
  width: 360px;
  height: 360px;
  margin: 0 40px 32px;
}
.booth-description {
  margin-top: 1rem;
  font-size: 1.25rem;
}

@media only screen and (max-width: 1024px) {
  .booth-info  {
    max-width: 380px;
  }
}

@media only screen and (max-width: 600px) {
  .booth-info  {
    max-width: 300px;
  }
}
</style>
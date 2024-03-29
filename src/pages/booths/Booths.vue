<template>
  <BoothPageBase shuffle-enabled type="booths" :page="page" :max-page="maxPage" :update-page="updatePage">
    <div v-if="booths?.length > 0" class="booth-list">
      <div v-for="(booth, i) in booths" :key="i" class="booth-item">
        <BoothCard :booth="booth" :color="getCardColor(booth, i)" />
      </div>
      <div v-if="inHome" class="booth-separator">
        <PMOSeparator vertical />
      </div>
    </div>
    <div class="booth-empty" v-else>暂无摊位。</div>
  </BoothPageBase>
</template>

<script lang="ts">
import { defineComponent } from "vue"

import HomePageBase from "../../components/HomePageBase.vue"
import { getSellers, Seller } from "../../utils/models"
import { shuffle } from "../../utils/math"
import { getQueryPage, inHome as isInHome, scrollIntoView } from "../../utils/view"
import BoothPageBase from "./BoothPageBase.vue"
import ImageView from "../../components/ImageView.vue"
import BoothCard from "../../components/BoothCard.vue"
import PMOSeparator from "../../components/PMOSeparator.vue"

const ItemsPerPage = 10

const sortSellers = (sellers: Seller[]): Seller[] => {
  sellers.sort((a, b) => {
    const aid = a.seller_id
    const bid = b.seller_id
    if (aid.length === 0) {
      if (bid.length === 0) {
        return a.id - b.id
      }
      return 1
    } else if (bid.length === 0) {
      return -1
    }
    return aid.localeCompare(bid)
  })
  const sorts: [Seller[], Seller[], Seller[]] = [[], [], []]
  for (const x of sellers) {
    sorts[x.seller_id.startsWith("A") ?
      0 : x.seller_id.startsWith("B") ?
        1 : 2].push(x)
  }
  let ii = [0, 0, 0]
  let c = sorts.findIndex((x) => x.length > 0)
  return sellers.map(() => {
    const x = sorts[c][ii[c]++]
    if (c === 0) {
      c = ii[1] < sorts[1].length ? 1 : ii[0] < sorts[0].length ? 0 : 2
    } else if (c === 1) {
      c = ii[0] < sorts[0].length ? 0 : ii[1] < sorts[1].length ? 1 : 2
    }
    return x
  })
}

export default defineComponent({
  name: "Booths",
  components: {
    ImageView,
    BoothPageBase,
    HomePageBase,
    BoothCard,
    PMOSeparator
  },
  data() {
    const inHome = isInHome()
    return {
      inHome,
      page: 0,
      maxPage: 0,
      booths: [] as Seller[],
      public: false,
      allBooths: [] as Seller[]
    }
  },
  methods: {
    updatePage(page: number) {
      if (page === -1) {
        this.allBooths = shuffle(this.allBooths)
        this.booths = this.allBooths.slice(0, 4)
        return
      }
      this.page = page
      this.booths = this.allBooths.slice(
        (page - 1) * ItemsPerPage,
        page * ItemsPerPage
      )
    },
    getCardColor(booth: Seller, i: number) {
      return booth.seller_id.startsWith("A")
        ? "red" : booth.seller_id.startsWith("B") ?
          "blue" : i % 2 === 0 ? "red" : "blue"
    }
  },
  async mounted() {
    const sellers = await getSellers()
    const allBooths = Array.from(Object.values(sellers))
    if (this.inHome) {
      this.allBooths = shuffle(allBooths)
      this.booths = allBooths.slice(0, 4)
    } else {
      this.allBooths = sortSellers(allBooths)
      this.maxPage = Math.ceil(allBooths.length / ItemsPerPage)
      const page = getQueryPage(this.$route, this.maxPage)
      this.updatePage(page)
      scrollIntoView()
    }
  },
})
</script>

<style scoped>
.booth-list {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  max-width: 900px;
  position: relative;
}

.booth-separator {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  display: flex;
  z-index: 0;
}

.booth-separator>div {
  margin: auto;
}

.booth-empty {
  margin: 80px auto auto;
  font-size: 2rem;
}

.booth-item {
  z-index: 1;
  display: flex;
  margin: auto;
  margin-bottom: 64px;
  width: 45%;
}

.booth-item>div {
  width: 100%;
}

.booth-item:nth-child(odd) {
  margin-left: 0;
  margin-right: auto;
  flex-direction: row-reverse;
}

.booth-item:nth-child(even) {
  margin-left: auto;
  margin-right: 0;
  flex-direction: row;
}

@media only screen and (max-width: 1280px) {
  .booth-item {
    margin-top: 48px;
  }
}


@media only screen and (max-width: 600px) {
  .booth-item {
    width: 200px;
  }

  .booth-item:nth-child(odd),
  .booth-item:nth-child(even) {
    flex-direction: row;
    margin: 12px auto 12px;
  }
}
</style>

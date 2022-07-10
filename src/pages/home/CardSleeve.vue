<template>
  <CommonInfoPage
    class="page-common"
    name="cardsleeve"
    title="卡套宣传"
    title2="“一名优秀的商人，会非常了解情报有多重要的。”——by 望罗"
  >
    <template v-slot:background>
      <svg class="background-dash" viewBox="0 0 1920 700">
        <image
          x="0px"
          y="64px"
          width="1919px"
          height="252px"
          xlink:href="../../assets/background-dash/4.png"
        />
        <image
          xlink:href="../../assets/page-backgrounds/cardsleeve.png"
          x="0"
          y="0"
          height="700"
          width="1920"
        />
      </svg>
    </template>
    <p>
      <span></span
      >最近宝可梦卡牌简体字相关的小道消息越来越浓厚，pmo主办组中也有不少小伙伴近期入坑了宝可梦卡牌，于是我们决定尝试启动特别的ptcg应援企划！
    </p>
    <figure>
      <img src="../../assets/cardsleeve/sample.png" alt="卡套宣传" />
    </figure>
    <p><span></span>限量300套，魔都PMO2022限定款宝可梦卡牌用卡套！</p>
    <p>将会随同PMO2022门票的预售同时开启预约！</p>
    <br />
    <p>
      <span></span
      >卡套将以符合宝可梦卡牌的大小（66*92）进行制作，以31张/套的形式进行封包
    </p>
    <p>
      <span class="gold">#若以宝可梦卡牌对战中使用为目的，需购买2套。</span>
    </p>
    <p>
      <span></span
      >图面更将附有镭射效果，无论在卡牌对战中使用还是收纳于卡册中，都炫目夺人！
    </p>
    <SmallHeader class="common-header">注意事项</SmallHeader>
    <ul>
      <li>每个ID<span class="gold">限购5套</span>；</li>
      <li>
        <span></span>预约后将于魔都PMO2022当天凭<span class="gold"
          >订单信息</span
        >在官摊领取；
      </li>
      <li>也可选择邮寄，但发货时间将在魔都PMO2022结束后；</li>
      <li>若因不可抗力导致魔都PMO2022延期或取消线下活动，发货日将另行通知；</li>
      <li>
        <span></span>若于9月18日前预约量<span class="gold">未满80套</span
        >的场合，企划将流产，订金将全部原路退还；
      </li>
      <li>
        <span></span>若于9月18日前预约量<span class="gold">满足80套</span
        >，但于魔都PMO2022当日<span class="gold">未满300套</span
        >的场合，将以现货形式于魔都PMO2022当日进行贩卖。
      </li>
    </ul>
  </CommonInfoPage>
</template>

<script setup lang="ts">
import CommonInfoPage from "../../components/CommonInfoPage.vue"
import SmallHeader from "../../components/SmallHeader.vue"
</script>

<style scoped></style>

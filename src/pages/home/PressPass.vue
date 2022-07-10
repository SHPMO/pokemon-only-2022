<template>
  <CommonInfoPage
    name="presspass"
    title="媒体证"
    title2="魔都 PMO 2022 开设媒体证申请"
  >
    <template v-slot:background>
      <svg class="background-dash" viewBox="0 0 1920 700">
        <image
          x="0px"
          y="64px"
          width="1920px"
          height="317px"
          xlink:href="../../assets/background-dash/3.png"
        />
        <image
          xlink:href="../../assets/page-backgrounds/presspass.png"
          x="0"
          y="0"
          height="700"
          width="1920"
        />
      </svg>
    </template>
    <SmallHeader>申请条件</SmallHeader>
    <ul>
      <li>
        <span>以公司或个人为主体运营的自媒体账号</span
        ><span class="gold"
          >（包括但不限于网站、客户端、微信公众号、微博、B站、抖音等）</span
        >，运营主体账号粉丝数需达5千人及以上，且需要达到一定互动量。
      </li>
      <li>该账号已发表内容中必须含有一定含量的宝可梦相关内容。</li>
      <li>活动结束后的一个月内需要发布魔都PMO相关的图文/视频报道。</li>
    </ul>
    <SmallHeader>申请注意</SmallHeader>
    <p>
      <span></span>请将以下情报填写完毕，以私信的方式发送至<span class="gold"
        >wb@洛托姆是宇宙的中心俱乐部</span
      >或加入申请群：<span class="gold">715624272</span
      >将内容发送至管理员【<span class="gold">洛托姆是宇宙的中心俱乐部部长</span
      >】。
    </p>
    <ul>
      <li>自媒体账号所在平台</li>
      <li>账号id</li>
      <li>曾经发表过的报道或视频链接（3~5条）</li>
    </ul>
    <SmallHeader>特别注意</SmallHeader>
    <ul>
      <li>每个自媒体账号可申请的人员上限为2人。</li>
      <li>申请时间为即日起至2022年10月9日。</li>
      <li>审核时间为一周。</li>
      <li>审核通过后的媒体人员于活动当日领取媒体证，具体时间另行通知。</li>
      <li>
        <span></span
        >活动当日媒体证需要佩戴在显眼位置，同时持有媒体证的人员仍需要进行进出场审核。
      </li>
      <li>
        <span></span
        >媒体证仅限申请人使用，禁止交易与转让。组委会保留对转让证件进行罚没，并请违规记者离场的权利。
      </li>
      <li>以上申请条件仅供参考，组委会对相关标准享有最终解释权</li>
    </ul>
  </CommonInfoPage>
</template>

<script setup lang="ts">
import CommonInfoPage from "../../components/CommonInfoPage.vue"
import SmallHeader from "../../components/SmallHeader.vue"
</script>

<style scoped></style>

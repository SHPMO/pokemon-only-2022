<template>
  <HomePageBase class="page-tickets" name="tickets" title="票务信息">
    <svg class="background-dash" viewBox="0 0 1920 916">
      <image
        x="0px"
        y="297px"
        width="1919px"
        height="252px"
        xlink:href="../../assets/background-dash/4.png"
      />
      <image
        x="0px"
        y="0px"
        width="142px"
        height="916px"
        xlink:href="../../assets/background-dash/5.png"
      />
    </svg>
    <template v-slot:title>
      <a
        v-if="ticketLink"
        class="tickets-purchase"
        :href="ticketLink"
        target="_blank"
      >
        点此购票
      </a>
    </template>
    <svg class="tickets-background" viewBox="0 0 1920 1156">
      <image
        xlink:href="../../assets/page-backgrounds/tickets.png"
        x="60"
        y="0"
        height="1156"
        width="1464"
      />
    </svg>
    <ul class="ticket-list">
      <div class="ticket-separator" />
      <li class="ticket-item">
        <div class="ticket-number highlighted">Ticket 1</div>
        <h3>普通入场票</h3>
        <div class="ticket-price highlighted">预售 50 RMB</div>
        <ul class="ticket-content">
          <li>含<span class="highlighted">入场票*1</span></li>
          <li class="highlighted">入场特典*1</li>
        </ul>
      </li>
      <div class="ticket-separator" />
      <li class="ticket-item">
        <div class="ticket-number highlighted">Ticket 2</div>
        <h3>普通入场票</h3>
        <div class="ticket-price highlighted">现场 70 RMB</div>
        <ul class="ticket-content">
          <li>含<span class="highlighted">入场票*1</span></li>
          <li class="highlighted">入场特典*1</li>
        </ul>
      </li>
      <div class="ticket-separator" />
      <li class="ticket-item">
        <div class="ticket-number highlighted">Ticket 3</div>
        <h3>舞台区入场票</h3>
        <div class="ticket-price highlighted">50 RMB</div>
        <ul class="ticket-content">
          <li>含<span class="highlighted">入场票*1</span></li>
          <li class="highlighted">入场特典*1</li>
          <li class="highlighted">舞台区座位整理券*1</li>
        </ul>
        <div class="ticket-help-text gray">
          # 仅网络贩售 / 每个 ID 最多可拍付 3 份
        </div>
      </li>
      <div class="ticket-separator" />
      <li class="ticket-item">
        <div class="ticket-number highlighted">Ticket 4</div>
        <h3>VIP 入场票</h3>
        <div class="ticket-price highlighted">预售 120 RMB</div>
        <ul class="ticket-content">
          <li>含<span class="highlighted">入场票*1</span></li>
          <li class="highlighted">提前入场资格</li>
          <li class="highlighted">VIP 入场特典</li>
          <li class="highlighted">舞台区前排固定座位整理券*1</li>
        </ul>
        <div class="ticket-help-text gray">
          # 仅网络贩售 / 限量 40 份 /<br />每个 ID 最多可拍付 2 份
        </div>
      </li>
      <div class="ticket-separator" />
      <li class="ticket-item">
        <div class="ticket-number highlighted">Ticket 5</div>
        <h3>对战券</h3>
        <div class="ticket-price highlighted">5 RMB</div>
        <ul class="ticket-content">
          <li>含<span class="highlighted">现场对战区比赛资格*1</span></li>
        </ul>
        <div class="ticket-help-text gray">
          # 单拍不发货 / <br />同笔订单内对战券数量多于门票数不发货
        </div>
      </li>
      <div class="ticket-separator" />
    </ul>
    <ul class="ticket-info">
      <li>
        需要参加对战区比赛的游客，请在购买门票的同时，将“<span class="red"
          >加购对战券</span
        >”加入购物车并一起支付。
      </li>
      <li>
        在收到票后，以《<span class="red">魔都PMO2022报名 + 昵称</span
        >》为邮件名，发送邮件到<a class="red" href="mailto:nebby@getdaze.org"
          >nebby@getdaze.org</a
        >。
      </li>
      <li>
        邮件中需要包含：门票ID号 | 对战券ID号 | 门票 + 对战券照片 | 个人昵称 |
        个人QQ号 ，以作为报名的验证和方便进行后期通知。
      </li>
      <li>
        另外有少量普通入场票的实体店寄卖<span class="gray"
          >（不设置舞台区入场票和VIP入场票）</span
        >。
      </li>
    </ul>
  </HomePageBase>
</template>

<script>
import HomePageBase from "../../components/HomePageBase.vue"

const PurchasingLink = ""

export default {
  name: "Tickets",
  components: {
    HomePageBase,
  },
  setup() {
    return {
      ticketLink: PurchasingLink,
    }
  },
}
</script>

<style scoped>
.page-tickets {
  margin-top: 172px;
}

.background-dash {
  margin-top: -472px;
}

.tickets-background {
  margin-left: auto;
  margin-right: auto;
  width: 100%;
  height: auto;
  z-index: 0;
  text-align: center;
}

.tickets-purchase {
  margin-top: 20px;
  color: #ffffff;
  background-color: #21222c;
  font-weight: bold;
  border-radius: 10px;
  font-size: 24px;
  padding: 8px 20px;
  z-index: 1;
}

.ticket-list {
  list-style: none;
  display: flex;
  align-items: start;
}

.ticket-item {
  width: 280px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.ticket-separator {
  position: relative;
  width: 3px;
  height: 330px;
  border-radius: 50%;
  background-color: #18171b;
}

.highlighted {
  color: #d31751;
}

.ticket-item:nth-child(4n) .highlighted {
  color: #0f65fd;
}

.ticket-number {
  margin-top: 38px;
  text-transform: uppercase;
  font-size: 15px;
  font-weight: bold;
}

.ticket-item > h3 {
  font-size: 28px;
  margin: 0;
}

.ticket-price {
  margin-top: 4px;
  font-size: 20px;
  font-weight: bold;
}

.ticket-content {
  margin-top: 28px;
  height: 116px;
  padding: 0;
  list-style: none;
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: 15px;
  font-weight: bold;
}

.ticket-help-text {
  text-align: center;
  font-size: 10px;
}

.ticket-info {
  list-style: none;
  font-size: 20px;
  font-weight: bold;
  line-height: 61px;
}

.ticket-info > li {
  background: url("../../assets/common/icon-flower.png") no-repeat left center;
  padding-left: 52px;
}
</style>

<style>
.page-tickets > .title-container {
  left: unset;
  right: 5%;
  width: 20%;
  padding-right: 20px;
  /* align-items: end; */
}
</style>

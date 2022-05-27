<template>
  <footer id="footer">
    <div class="copyright">© 银河队文艺组</div>
    <img class="logo" src="../assets/common/logo-white.png" alt="">
    <ul class="links">
      <li class="link">
        <a href="https://www.weibo.com/SHPMO" target="_blank">
          <img class="weibo-logo" src="../assets/footer/weibo.png" alt="">
          <span>@魔都PMO_梦天庆典</span>
        </a>
      </li>
      <li class="link">
        <a href="https://www.weibo.com/u/7001510374" target="_blank">
          <img class="weibo-logo" src="../assets/footer/weibo.png" alt="">
          <span>@洛托姆是宇宙的中心俱乐部</span>
        </a>
      </li>
    </ul>
  </footer>
</template>

<script lang="ts">
import { defineComponent } from "vue"

export default defineComponent({
  name: "Footer",
  components: {}
})
</script>

<style scoped>
#footer {
  position: relative;
  width: 100%;
  height: 196px;
  background: #282828;
  display: flex;
  align-items: center;
  color: #ffffff;
}

.copyright {
  position: absolute;
  margin: 0;
  width: 25%;
  max-width: 186px;
  left: 5%;
  text-align: center;
}

.logo {
  max-width: 301px;
  height: auto;
  margin: auto;
}

.links {
  position: absolute;
  list-style: none;
  padding: 0;
  right: 5%;
  margin: 0;
}

.link {
  margin-top: 24px;
}

.link:nth-child(1) {
  margin-top: 0;
}

.link > a {
  display: flex;
  align-items: center;
  height: 18px;
  line-height: 18px;
  font-size: 14px;
  color: #ffffff;
}

.weibo-logo {
  margin-right: 5px;
}

@media only screen and (max-width: 768px) {
  .links {
    position: relative;
    right: 0;
    margin: auto;
  }
}
@media only screen and (max-width: 600px) {
  .link > a {
    font-size: 10px;
  }
}
</style>

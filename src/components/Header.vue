<template>
  <div class="headerCont">
    <div class="landing lang-max">
      <div class="header">
        <img :src="swanLogo" class="logoImg" alt='swan' @click="system.$commonFun.goLink('https://www.swanchain.io/')" />
        <div class="el-menu-right">
          <a href="https://docs.swanchain.io/swan-testnet/swan-saturn-testnet" target="_blank" class="describe">Docs</a>
          <a href="https://saturn-explorer.swanchain.io/" target="_blank" class="describe">Explorer</a>
          <a href="https://docs.swanchain.io/swan-testnet/swan-saturn-testnet/faq" target="_blank" class="describe">FAQ</a>
          <a href="https://linktr.ee/swan_chain" target="_blank" class="describe">Community</a>
          <a href="https://mailchi.mp/swanchain/swan-chain" target="_blank" class="describe">Sign Up for Newsletter</a>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { defineComponent, computed, onMounted, watch, ref, reactive, getCurrentInstance } from 'vue'
import { useStore } from "vuex"
import { useRouter, useRoute } from 'vue-router'
export default defineComponent({
  setup () {
    const store = useStore()
    const bodyWidth = ref(document.body.clientWidth < 992)
    const system = getCurrentInstance().appContext.config.globalProperties
    const route = useRoute()
    const router = useRouter()
    const swanLogo = require("@/assets/images/icons/SWAN_logo_01.png")

    onMounted(() => { })
    return {
      swanLogo,
      system
    }
  },
  components: {}
})
</script>
<style lang="less" scoped>
.header {
  margin: auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.1rem 10%;
  @media screen and (max-width: 600px) {
    padding: 0.1rem;
  }
  .logoImg {
    height: 0.38rem;
    cursor: pointer;
    @media screen and (max-width: 600px) {
      height: 24px;
    }
  }
  .el-menu-right {
    display: flex;
    align-items: center;
    a {
      color: #fff;
      margin-left: 0.5rem;
      @media screen and (max-width: 600px) {
        margin-left: 0.25rem;
      }
      &:first-child {
        margin-left: 0;
      }
      &:hover {
        color: #447dff;
      }
    }
  }
}
</style>

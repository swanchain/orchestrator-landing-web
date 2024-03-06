<template>
  <section id="container">
    <div class="relative-style">
      <div class="bg">
        <svg width="1912" height="1912" viewBox="0 0 1912 1912" fill="none" xmlns="http://www.w3.org/2000/svg">
          <g filter="url(#filter0_f_120_42)">
            <circle cx="956" cy="956" r="456" fill="#232753" />
          </g>
          <defs>
            <filter id="filter0_f_120_42" x="0" y="0" width="1912" height="1912" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
              <feFlood flood-opacity="0" result="BackgroundImageFix" />
              <feBlend mode="normal" in="SourceGraphic" in2="BackgroundImageFix" result="shape" />
              <feGaussianBlur stdDeviation="250" result="effect1_foregroundBlur_120_42" />
            </filter>
          </defs>
        </svg>
      </div>
      <div class="bg n">
        <svg width="1912" height="1912" viewBox="0 0 1912 1912" fill="none" xmlns="http://www.w3.org/2000/svg">
          <g filter="url(#filter0_f_120_42)">
            <circle cx="956" cy="956" r="456" fill="#232753" />
          </g>
          <defs>
            <filter id="filter0_f_120_42" x="0" y="0" width="1912" height="1912" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
              <feFlood flood-opacity="0" result="BackgroundImageFix" />
              <feBlend mode="normal" in="SourceGraphic" in2="BackgroundImageFix" result="shape" />
              <feGaussianBlur stdDeviation="250" result="effect1_foregroundBlur_120_42" />
            </filter>
          </defs>
        </svg>
      </div>

      <div class="container-banner">
        <div class="w-50">
          <div class="title font-black">Welcome to <br />SWAN SATURN TESTNET</div>
          <p class="font-bold">Share Prize Pool of 3,000,000 SWAN</p>
          <div class="time flex-row center">
            <span class="font-bold">22nd January, 00:00 (EST) - 22nd March, 00:00 (EST)</span>
          </div>
          <div class="desc describe">
            Saturn Testnet is the public testnet of Swan Chain, a layer 2 AI computing blockchain with Superchain technology. Our mission is to rigorously test and showcase the capabilities of Swan Chain, with the help of the developer community.
          </div>
          <a href="https://docs.swanchain.io/swan-testnet/swan-saturn-testnet" target="_blank" class="join-a">JOIN TESTNET</a>
        </div>
        <div class="w-100"></div>
      </div>

      <div class="container-swiper">
        <div class="lang-max">
          <p class="tit font-bold uppercase">Funded By</p>
          <el-row class="block-cont row-bg">
            <el-col v-for="b in fundData" :key="b">
              <img :src="b.img" />
            </el-col>
          </el-row>
        </div>
      </div>

      <div class="container-area">
        <div class="lang-max">
          <h3 class="font-bold uppercase">How to Get Involved</h3>
          <div class="fe-none">
            <el-row :gutter="bodyWidth">
              <el-col :xs="24" :sm="12" :md="12" :lg="12" :xl="12" v-for="(card, c) in involvedData" :key="c">
                <div class="content flex-row nowrap" :class="{'is-disabled': card.disabled}">
                  <div class="icon-involved flex-row center">
                    <img :src="card.images" alt="">
                  </div>
                  <div class="area">
                    <h1 class="font-bold flex-row">{{card.title}}</h1>
                    <p class="describe">{{card.desc}}</p>
                    <div class="button-list">
                      <a v-for="b in card.list" :key="b" @click="involvedLink(card, b)" class="uppercase">[{{b.button}}]</a>
                    </div>
                  </div>
                </div>
              </el-col>
            </el-row>
          </div>
        </div>
      </div>

      <div class="container-area s">
        <div class="lang-max">
          <h3 class="font-bold uppercase">Rewards and Incentives</h3>
          <h5 class="weight-6">3,000,000 SWAN tokens allocated for various programs</h5>
          <el-row :gutter="rewardWidth" class="reward-style flex-row flex-start">
            <el-col :xs="24" :sm="8" :md="8" :lg="8" :xl="8" v-for="(reward, r) in rewardData" :key="r">
              <div class="content" :class="{'none': !reward.link}">
                <h1 class="small weight-6">{{reward.content}}</h1>
                <div class="link flex-row center">
                  <a @click="system.$commonFun.goLink(reward.link)" class="weight-6 uppercase">{{reward.button}}</a>
                </div>
              </div>
            </el-col>
          </el-row>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { defineComponent, ref, reactive, getCurrentInstance } from 'vue'
import { useStore } from "vuex"
import { useRouter, useRoute } from 'vue-router'
// import {
//   CircleCheck
// } from '@element-plus/icons-vue'
import { ElRow, ElCol } from 'element-plus'
export default defineComponent({
  components: {
    ElRow, ElCol
  },
  setup () {
    const store = useStore()
    const bodyWidth = ref(document.body.clientWidth <= 768 ? 40 : 80)
    const rewardWidth = ref(document.body.clientWidth <= 768 ? 20 : 28)
    const system = getCurrentInstance().appContext.config.globalProperties
    const route = useRoute()
    const router = useRouter()
    const involvedData = ref([
      {
        title: 'Become a computing provider',
        desc: 'Share your resources and earn income.',
        images: require('@/assets/images/icons/involved/involved-02.png'),
        list: [
          // {
          //   button: 'CHECK DASHBOARD',
          //   link: 'https://orchestrator.swanchain.io '
          // },
          {
            button: 'Register',
            link: 'https://docs.google.com/forms/d/e/1FAIpQLSdARmvfjo6w7pNMdL6qlmGHFbBcQwRhShCEjiy8MaMNEERe_A/viewform?usp=sf_link'
          },
          {
            button: 'VIEW GUIDE',
            link: 'https://docs.swanchain.io/orchestrator/as-a-computing-provider/computing-provider-setup'
          }
        ],
        disabled: false
      },
      {
        title: 'Join community events',
        desc: 'Participate, learn, and win SWAN tokens.',
        images: require('@/assets/images/icons/involved/involved-03.png'),
        list: [
          {
            button: 'DISCOVER MORE',
            link: 'https://discord.com/channels/867879887871672331/1186156859485343865'
          }
        ],
        disabled: false
      },
      {
        title: 'Provide feedback and suggestions',
        desc: 'Your input is valuable for shaping the future of Swan Chain.',
        images: require('@/assets/images/icons/involved/involved-07.png'),
        list: [
          {
            button: 'FEEDBACK NOW',
            link: 'https://docs.google.com/forms/d/e/1FAIpQLSdw6gTZL2Pzu2vAo3gWbva0oafbZ1PSvpS9ImRVQ_tk-UCIRA/viewform'
          }
        ],
        disabled: false
      },
      {
        title: 'Bridge tokens',
        desc: 'Move assets freely between blockchains.',
        images: require('@/assets/images/icons/involved/involved-01.png'),
        list: [
          {
            button: 'BRIDGE NOW',
            link: 'https://bridge.swanchain.io/'
          },
          {
            button: 'VIEW GUIDE',
            link: 'https://docs.swanchain.io/swan-testnet/swan-saturn-testnet/before-you-get-started/bridge-tokens'
          }
        ],
        disabled: false
      },
      {
        title: 'Deploy smart contracts and dApps',
        desc: 'Use our developer tools and resources.',
        images: require('@/assets/images/icons/involved/involved-04.png'),
        list: [
          {
            button: 'VIEW GUIDE',
            link: 'https://docs.swanchain.io/development-resource/quickstarts/deploying-your-first-smart-contract-with-remix'
          }
        ],
        disabled: false
      },
      {
        title: 'Try and use dApps',
        desc: 'Lagrange and others are waiting for you.',
        images: require('@/assets/images/icons/involved/involved-05.png'),
        list: [
          {
            button: 'TRY NOW',
            link: 'https://lagrangedao.org/'
          }
        ],
        disabled: false
      },
      {
        title: 'Claim faucet tokens',
        desc: 'Get free SWAN for testing purposes.',
        images: require('@/assets/images/icons/involved/involved-06.png'),
        list: [
          {
            button: 'CLAIM NOW',
            link: 'https://discord.gg/37ze379kqW'
          },
          {
            button: 'VIEW GUIDE',
            link: 'https://docs.swanchain.io/swan-testnet/swan-saturn-testnet/before-you-get-started/claim-tokens'
          }
        ],
        disabled: false
      }
    ])
    const rewardData = ref([
      {
        content: 'Transaction Drive Program',
        button: 'EXPLORE MORE',
        link: 'https://docs.swanchain.io/swan-testnet/swan-saturn-testnet/transaction-drive-program'
      },
      {
        content: 'Community and Educational Events',
        button: 'EXPLORE MORE',
        link: 'https://discord.com/channels/867879887871672331/1186156859485343865'
      },
      {
        content: 'Computing Provider Program',
        button: 'EXPLORE MORE',
        link: 'https://docs.swanchain.io/swan-testnet/swan-saturn-testnet/computing-provider-program'
      },
      {
        content: 'Partnership and Integration Program',
        button: 'EXPLORE MORE',
        link: 'https://docs.swanchain.io/swan-testnet/swan-saturn-testnet/partnership-and-integration-program'
      },
      {
        content: 'Developer Grant Program',
        button: 'EXPLORE MORE',
        link: 'https://docs.swanchain.io/swan-testnet/swan-saturn-testnet/developer-grant-program'
      },
    ])
    const fundData = ref([
      {
        img: require('@/assets/images/icons/funded/funded-01.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-02.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-03.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-04.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-05.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-06.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-07.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-08.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-09.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-10.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-11.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-12.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-13.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-14.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-15.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-17.png')
      },
      {
        img: require('@/assets/images/icons/funded/funded-18.png')
      }
    ])

    function involvedLink (row, content) {
      if (row.disabled) return
      else system.$commonFun.goLink(content.link)
    }
    return {
      system,
      bodyWidth,
      rewardWidth,
      involvedData,
      rewardData,
      fundData,
      involvedLink
    }
  }
})
</script>

<style lang="less" scoped>
#container {
  padding: 0 0 1.6rem;
  font-size: 18px;
  letter-spacing: 0;
  word-break: break-word;
  line-height: 1.2;
  @media screen and (max-width: 1200px) {
    font-size: 16px;
  }
  .relative-style {
    position: relative;
    .bg {
      position: absolute;
      top: 22%;
      left: 1%;
      width: 98%;
      z-index: 1;
      @media screen and (max-width: 768px) {
        left: 0%;
        right: 0%;
        width: 100%;
      }
      &.n {
        top: 50%;
        left: 0%;
        width: 100%;
      }
      svg {
        width: 100%;
        height: auto;
      }
    }
    .swan-logo {
      display: block;
      width: 200px;
      margin: 0 0 0.3rem;
    }
    .container-banner {
      position: relative;
      max-width: 1620px;
      padding: 1.25rem 0 1.95rem;
      margin: auto;
      z-index: 7;
      .w-100 {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        z-index: 0;
        background-image: url(../../../assets/images/icons/animate_01.png),
          url(../../../assets/images/icons/animate_03.png),
          url(../../../assets/images/icons/animate_02.png);
        background-position: 16.6% 23%, 7% 90%, 90% 85%;
        background-repeat: no-repeat, no-repeat, no-repeat;
        background-size: 11.4%, 20%, 19%;
        animation: floating 3.5s ease-in-out infinite;
        @media screen and (max-width: 1024px) {
          background-position: 5% 15%, 15% 75%, 95% 60%;
        }
        @media screen and (max-width: 599px) {
          background-position: 5% 15%, 15% 75%, right 40%;
        }
      }
      .w-50 {
        position: relative;
        width: 55%;
        max-width: 900px;
        min-width: 310px;
        margin: auto;
        text-align: center;
        z-index: 1;
        .title {
          font-size: 0.65rem;
          text-transform: uppercase;
          line-height: 1.15;
        }
        p {
          padding: 0.1rem 0 0.5rem;
          font-size: 0.32rem;
        }
        .desc {
          width: 90%;
          max-width: 7.5rem;
          margin: auto;
          line-height: 1.7;
        }
        .join-a {
          display: inline-block;
          padding: 0.15rem 0.3rem;
          margin: 0.24rem auto 0.6rem;
          background-color: #447dff;
          font-family: inherit;
          font-size: 0.18rem;
          font-weight: 600;
          border: 0.02rem solid #447dff;
          border-radius: 1rem;
          color: #fff;
          text-transform: uppercase;
          line-height: 1;
          transition: all 0.2s;
          &:hover {
            background-color: transparent;
            color: #447dff;
          }
        }
        .time {
          margin: 0 0 0.3rem;
          span {
            padding: 0.12rem 0.55rem;
            font-size: 0.2rem;
            border: 1px solid #fff;
            border-radius: 1rem;
            color: #fff;
            word-break: break-word;
            white-space: nowrap;
          }
        }
      }
    }
    .width {
      width: 70%;
      min-width: 300px;
      margin: auto;
    }
    .container-swiper {
      position: relative;
      padding: 1.4rem 0 0;
      z-index: 7;
      @media screen and (max-width: 768px) {
        padding: 0;
      }
      .tit {
        padding: 0.24rem 0 0.3rem;
        font-size: 0.26rem;
        text-align: center;
      }
      .block-cont {
        margin: 0 auto;
        .el-col {
          margin: 0.1rem 0;
          max-width: 11.11%;
          flex: 0 0 11.11%;
          @media screen and (max-width: 1024px) {
            max-width: 12.5%;
            flex: 0 0 12.5%;
          }
          @media screen and (max-width: 992px) {
            max-width: 16.66%;
            flex: 0 0 16.66%;
          }
          @media screen and (max-width: 768px) {
            max-width: 20%;
            flex: 0 0 20%;
          }
          @media screen and (max-width: 600px) {
            max-width: 25%;
            flex: 0 0 25%;
          }
          @media screen and (max-width: 540px) {
            max-width: 33.33%;
            flex: 0 0 33.33%;
          }
          img {
            width: 94%;
            margin: 0 auto;
          }
        }
      }
    }
    .container-area {
      position: relative;
      padding: 1.5rem 0 0;
      overflow: hidden;
      z-index: 7;
      &.s {
        padding: 1.5rem 0 0;
      }
      .lang-max {
        position: relative;
        z-index: 7;
      }
      h3 {
        font-size: 0.26rem;
      }
      h5 {
        padding: 0.05rem 0 0;
        font-size: 0.16rem;
      }
      .fe-none {
        padding: 0 5%;
        .el-row {
          margin: 0 auto;
          .el-col {
            margin: 0.8rem 0 0;
            .content {
              &.is-disabled {
                cursor: no-drop;
                .icon-involved {
                  img {
                    opacity: 0.5;
                  }
                }
                .area {
                  color: #9a9fab;
                  p {
                    color: inherit;
                  }
                  .button-list {
                    a {
                      cursor: no-drop;
                      &:hover {
                        text-decoration: none;
                      }
                    }
                  }
                }
              }
              .icon-involved {
                width: 35%;
                img {
                  width: 55%;
                }
              }
              .area {
                width: 65%;
                color: #447dff;
                h1 {
                  font-size: 0.28rem;
                  line-height: 0.3rem;
                  &.small {
                    font-size: 0.2rem;
                  }
                }
                p {
                  margin: 0.1rem 0 0.2rem;
                  font-size: 0.14rem;
                  color: #f5f5f5;
                  line-height: 0.18rem;
                }
                .button-list {
                  a {
                    margin: 0 0.16rem 0.16rem 0;
                    font-size: 0.16rem;
                    color: inherit;
                    white-space: nowrap;
                    &:hover {
                      text-decoration: underline;
                    }
                  }
                }
              }
            }
          }
        }
      }
      .reward-style {
        padding: 1rem 15% 0.2rem;
        .el-col {
          margin: 0.4rem 0 0;
          .content {
            position: relative;
            height: calc(100% - 1.2rem);
            padding: 0.35rem 0.3rem 0.85rem;
            background-color: #447dff;
            border-radius: 0.15rem;
            text-align: center;
            &.none {
              background-color: #313953;
              .link {
                a {
                  background-color: transparent;
                  color: #447dff;
                  cursor: no-drop;
                  border-color: transparent;
                  &:hover {
                    color: #447dff;
                  }
                }
              }
            }
            h1 {
              min-height: 0.52rem;
              padding: 0 0 0.3rem;
              font-size: 0.2rem;
              line-height: 0.26rem;
            }
            .link {
              position: absolute;
              bottom: 0.25rem;
              left: 0;
              right: 0;
              a {
                height: 0.4rem;
                padding: 0 0.3rem;
                background-color: #fff;
                font-size: 0.15rem;
                line-height: 0.4rem;
                color: #447dff;
                border: 2px solid #fff;
                border-radius: 1rem;
                transition: all 0.2s;
                &:hover {
                  background-color: transparent;
                  color: #fff;
                }
              }
            }
          }
        }
      }
    }
  }
}
</style>

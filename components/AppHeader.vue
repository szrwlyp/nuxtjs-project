<script setup lang="ts">
import { ref } from 'vue'

const navList = ref([
  { title: '首页', to: '/' },
  {
    title: '解决方案',
    children: [
      { title: '电子政务解决方案', path: '' },
      { title: '人大履职解决方案', path: '' },
      { title: '食药监管解决方案', path: '' },
      { title: '智能化工程解决方案', path: '' },
    ],
  },
  {
    title: '关于超创',
    children: [
      { title: '公司简介', path: '' },
      { title: '企业文化', path: '' },
      { title: '资质荣誉', path: '' },
      { title: '招贤纳士', path: '' },
      { title: '合作伙伴', path: '' },
    ],
  },
  { title: '联系我们' },
])

// 当前选中的nav
const navCurrentIndex = ref(0)
const isShowBg = ref(false)
const openNav = (i: number, isChilder: boolean) => {
  navCurrentIndex.value = i
  console.log(i)
  isShowBg.value = isChilder
}
const closeNav = () => {
  navCurrentIndex.value = 100
  isShowBg.value = false
  console.log(navCurrentIndex.value)
}
</script>

<template>
  <div class="affix-placeholder">
    <header>
      <div class="h-navbar affix-top">
        <div class="logo">
          <img src="~assets/images/header/logo.jpg" alt="" />
        </div>
        <MenuComp></MenuComp>
        <nav class="cc-navbar">
          <ul>
            <template v-for="(item, index) in navList">
              <li
                :key="index"
                :class="[navCurrentIndex === index ? 'select' : '']"
                @click="openNav(index, item.children ? true : false)"
              >
                <div class="title">{{ item.title }}</div>
                <div v-if="item.children" class="nav-children">
                  <div class="c-list">
                    <div
                      v-for="(child, c_index) in item.children"
                      :key="c_index"
                      class="c-title"
                    >
                      <router-link :to="child.path" class="c-title-span">{{
                        child.title
                      }}</router-link>
                    </div>
                    <!-- <router-link
                    v-for="(child, index) in item.children"
                    :key="index"
                    :to="child.path"
                    >{{ child.title }}</router-link
                  > -->
                  </div>
                  <span class="close-icon" @click.stop="closeNav">X</span>
                </div>
              </li>
            </template>
          </ul>
        </nav>
      </div>
    </header>
    <div v-if="isShowBg" class="bg"></div>
  </div>
</template>

<style lang="scss" scoped>
header {
  width: 100%;
  position: relative;
  z-index: 120;
  background-color: #fff;
  font-size: 1em;
  height: 100%;
  border-bottom: 1px solid #e6e6e6;
  display: flex;
  padding: 0 15px;
}
.affix-placeholder {
  height: 78px;
  position: sticky;
  top: 0;
  z-index: 1000;
  .affix-top {
    height: 100%;
    position: relative;
    border: none;
    margin-bottom: 0;
    display: flex;
    width: 1200px;
    margin: 0 auto;
    justify-content: space-between;
    align-items: center;
    .logo {
      display: flex;
      align-items: center;
      img {
        width: 233px;
        height: 50px;
      }
    }
    .client-menu {
      display: none;
    }
    .cc-navbar {
      display: block;
      height: 100%;
      ul {
        display: flex;
        height: 100%;

        li {
          padding: 0 20px;
          position: relative;
          .title {
            cursor: pointer;
            display: flex;
            align-items: center;
            height: 100%;
          }
          .nav-children {
            width: 100%;
            padding: 30px 100px;
            background: #fff;
            position: fixed;
            left: 0;
            top: 78px;
            z-index: 1000;
            display: none;
            .c-list {
              display: flex;
              width: 70%;
              margin: auto;
              .c-title {
                flex: 1;
                padding: 0 20px;
                .c-title-span {
                  cursor: pointer;
                  color: #333333;
                }
              }
            }
            .close-icon {
              position: absolute;
              right: 90px;
              top: 10px;
              font-size: 24px;
              cursor: pointer;
            }
          }
        }
        .select {
          .nav-children {
            display: block;
          }
          &::after {
            content: '';
            position: absolute;
            bottom: -1px;
            left: 0;
            width: 100%;
            height: 2px;
            background: #c7000b;
          }
        }
      }
    }
  }

  .bg {
    background: rgba(0, 0, 0, 0.5);
    width: 100vw;
    height: 100vh;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 1;
  }
}

/* .navbar-toggle {
  margin-top: 16px;
  margin-bottom: 16px;
  width: 44px;
  height: 34px;
  position: relative;
  float: right;
  margin-right: 15px;
  padding: 9px 10px;

  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 4px;
  & > .icon-bar {
    position: absolute;
    top: 50%;
    left: 50%;
    margin-left: -11px;
    margin-top: 4px;
    background-color: #000;
    display: block;
    width: 22px;
    height: 2px;
    border-radius: 1px;
  }
  & > .icon-bar:nth-child(2) {
    -webkit-transform: rotate(0);
    -ms-transform: rotate(0);
    transform: rotate(0);
    margin-top: 0;
  }
  & > .icon-bar:nth-child(3) {
    opacity: 1;
  }
  & > .icon-bar:nth-child(4) {
    -webkit-transform: rotate(0);
    -ms-transform: rotate(0);
    transform: rotate(0);
  }
} */
/* @media (min-width: 1025px) {
  header .navbar {
    height: 78px;
    border-bottom: 1px solid #e6e6e6;
    margin-bottom: 0;
    border-radius: 0;
    .nav-container {
      position: relative;
    }
    .container {
      width: 93.705%;
    }
  }
} */

@media screen and (max-width: 1024px) {
  .affix-placeholder {
    height: 66px;
    .bg {
      display: none;
    }
    .h-navbar {
      .logo {
        img {
          width: 151px;
          height: 30px;
        }
      }
      .client-menu {
        display: block;
      }
      .cc-navbar {
        display: none;
      }
    }
  }
}
</style>

<script setup lang="ts">
import { ref } from 'vue'
const isClose = ref(false)
const navbarToggle = () => {
  isClose.value = !isClose.value
}
</script>

<template>
  <div class="client-menu">
    <button
      class="navbar-toggle"
      :class="{ 'navbar-close': isClose }"
      @click="navbarToggle"
    >
      <span class="icon-bar"></span>
      <span class="icon-bar"></span>
      <span class="icon-bar"></span>
    </button>

    <div class="fluid-container" :class="{ 'show-fluid': isClose }"></div>
  </div>
</template>

<style lang="scss" scoped>
.client-menu {
  position: relative;

  .fluid-container {
    position: fixed;
    top: 66px;
    right: 0;
    width: 0;
    height: 100vh;
    background: #f2f2f2;
    /* opacity: 0; */

    transition: all 0.6s ease-in-out;
  }
  .show-fluid {
    /* opacity: 1; */
    width: 100vw;
  }

  .navbar-toggle {
    width: 44px;
    height: 34px;
    position: relative;
    padding: 9px 10px;
    background-color: transparent;
    background-image: none;
    border: 1px solid transparent;
    border-radius: 4px;
    .icon-bar {
      display: block;
      width: 22px;
      height: 2px;
      border-radius: 1px;
      background-color: #000;
      margin-top: 4px;
    }
    & > .icon-bar:nth-child(1) {
      -webkit-transform: rotate(0);
      -ms-transform: rotate(0);
      transform: rotate(0);
      margin-top: 0;
    }
    & > .icon-bar:nth-child(2) {
      opacity: 1;
    }
    & > .icon-bar:nth-child(3) {
      -webkit-transform: rotate(0);
      -ms-transform: rotate(0);
      transform: rotate(0);
    }
  }
  .navbar-close {
    .icon-bar {
      position: absolute;
      top: 50%;
      left: 50%;
      margin-left: -11px;
      margin-top: -1px !important;
      background-color: #000;
    }
    & > .icon-bar:nth-child(1) {
      -webkit-transform: rotate(45deg);
      -ms-transform: rotate(45deg);
    }
    & > .icon-bar:nth-child(2) {
      opacity: 0;
    }
    & > .icon-bar:nth-child(3) {
      -webkit-transform: rotate(-45deg);
      -ms-transform: rotate(-45deg);
      transform: rotate(-45deg);
    }
  }
}
</style>

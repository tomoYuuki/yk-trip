<template>
  <div>
    <router-view v-slot="props">
      <keep-alive include="home">
        <component :is="props.Component"></component>
      </keep-alive>
    </router-view>
    <tab-bar
      v-show="!route.meta.isTabbarHidden"
      :tabbar-data="tabbarData"
    ></tab-bar>
    <!-- loading组件 -->
    <loading />
  </div>
</template>

<script setup>
import { RouterView, useRoute } from 'vue-router'
// 组件
import loading from './base-ui/loading/loading.vue'
import tabBar from './base-ui/tabBar/tab-bar.vue'
import tabbarData from '@/assets/data/tabbar.js'

const route = useRoute()
</script>

<style scoped></style>

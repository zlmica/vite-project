<template>
  <div class="p-2 bg-red-400 ">
    <router-link to="/" class="text-white">首页</router-link>
    <router-link to="/about" class="text-white ml-6 ">关于</router-link>
    <button class="text-white absolute right-10" @click="toggle">全屏</button>
  </div>
  <router-view></router-view>
</template>

<script setup>
import { useFullscreen } from '@vueuse/core'

const { isFullscreen, enter, exit, toggle } = useFullscreen()
</script>

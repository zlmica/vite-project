<template>
  <h1>关于页面</h1>
  <div>{{ x }}</div>
  <div>{{ y }}</div>
</template>

<script setup>
import { useMouse } from "../utils/mouse";
let { x, y } = useMouse();
</script>

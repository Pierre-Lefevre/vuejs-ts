<script setup lang="ts">
import { inject, ref } from "vue";
import Demo from "./Demo.vue";
const n = ref<"a">("a");
const onDemo = (firstname: string, lastname: string) => {};
inject<string>("demo");
const onClick = (e: MouseEvent) => {};
const div = ref<HTMLDivElement | null>(null);
</script>

<template>
  <div ref="div" @click="onClick"><Demo @demo="onDemo" v-model="n" />Lorem</div>
</template>

<style scoped></style>

<script setup lang="ts">
import { ref } from "vue";

let themeMode = ref("light-mode");
// let dayMode = ref(true);
const switchMode = () => {
  themeMode.value =
    themeMode.value === "light-mode" ? "dark-mode" : "light-mode";
  // dayMode.value = !dayMode.value;
  // console.log(dayMode.value);
};
</script>

<template>
  <div class="top-ele" :theme-mode="themeMode">
  <!-- <div class="top-ele"> -->
    <div class="sec-ele">
      <div v-for="i in [1, 2, 3]" :key="i" class="single-wrapper">
        <div class="user-avatar"></div>
        <div class="info-body">Lorem ipsum dolor sit, amet...</div>
      </div>
      <footer>
        <button @click="switchMode" class="btn-theme">切换</button>
      </footer>
    </div>
  </div>
</template>

<style scoped>
.top-ele[theme-mode="light-mode"] {
  --primary: #9ab7d9;
  --element: #0b1325;
  --surface: #f3f4f5;
}

.top-ele[theme-mode="dark-mode"] {
  --primary: #c4dbf5;
  --element: #d7d9e3;
  --surface: #0b1325;
}

/* .top-ele {
  --primary: v-bind("dayMode ? '#9ab7d9' : '#c4dbf5'");
  --element: v-bind("dayMode ? '#0b1325' : '#d7d9e3'");
  --surface: v-bind("dayMode ? '#f3f4f5' : '#0b1325'");
} */

.sec-ele {
  background-color: var(--surface);
}

.single-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
}

.user-avatar {
  width: 3.6vw;
  height: 3.6vw;
  margin: 0.4vw 0;
  border-radius: 50%;
  background-color: var(--primary);
}

.info-body {
  margin-left: 1vw;
  width: 18vw;
  height: 2.4vw;
  border: 1px solid var(--primary);
  border-radius: 16px;
  font-size: 1vw;
  color: var(--element);
  display: flex;
  justify-content: center;
  align-items: center;
}

footer {
  position: relative;
}

.btn-theme {
  position: relative;
  left: calc(60vw - 0.8vw);
  font-size: 0.2vw;
  padding: 0.6vw 0.4vw;
  background-color: var(--surface);
  border-radius: 50%;
  border: 2px solid var(--primary);
  color: var(--element);
  margin: 0.4vw 0vw;
}
/* 过渡动画 */
* {
  transition: 0.4s;
}
</style>

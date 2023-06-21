<script setup>
import { Icon } from '@iconify/vue'
</script>

<template>
  <footer>
    <div class="logo">Mamba Mentality</div>

    <div class="icons">
      <a href=""><Icon icon="mdi:github" /></a>
      <a href=""><Icon icon="ri:instagram-fill" /></a>
      <a href=""><Icon icon="mdi:linkedin" /></a>
      <a href=""><Icon icon="mdi:github" /></a>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: #fff;
  background: #000;
  margin-top: 100px;
  padding: 15px 30px;

  .logo {
    font-size: 1.1em;
    font-weight: 600;
  }

  .icons {
    display: flex;
    gap: 5px;

    a {
      color: #fff;
      font-size: 2em;
    }
  }
}
</style>

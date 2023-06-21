<script setup>
import Button from './DynamicButton.vue'
</script>

<template>
  <nav>
    <div class="logo">Mamba Mentality</div>
    <Button>Improve My Game</Button>
  </nav>
</template>

<style lang="scss" scoped>
nav {
  background-color: black;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 30px;

  .logo {
    color: #fff;
    font-size: 1.3em;
    font-weight: 600;
  }
}
</style>

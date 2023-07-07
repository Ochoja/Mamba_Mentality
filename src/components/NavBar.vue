<script setup>
import { ref } from 'vue'
import Button from './DynamicButton.vue'
import TrainingModal from './TrainingModal.vue'

const isModalOpen = ref(false)

const closeModal = () => (isModalOpen.value = false)
</script>

<template>
  <nav>
    <div class="logo"><RouterLink to="/">Mamba Mentality</RouterLink></div>

    <div class="more">
      <div class="about"><RouterLink to="/about">About</RouterLink></div>
      <Button @click="isModalOpen = true">Improve My Game</Button>
    </div>
  </nav>

  <Teleport to="body" v-if="isModalOpen">
    <TrainingModal @closeModal="closeModal"></TrainingModal>
  </Teleport>
</template>

<style lang="scss" scoped>
nav {
  background-color: black;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 30px;

  .logo {
    font-size: 1.3em;
    font-weight: 600;

    a {
      color: #fff;
      text-decoration: none;
    }
  }

  .more {
    display: flex;
    align-items: center;
    gap: 50px;

    a {
      color: #fff;
      text-decoration: none;
      font-weight: 700;
    }

    a:hover {
      text-decoration: underline;
      color: var(--secondary-color);
    }
  }
}
</style>

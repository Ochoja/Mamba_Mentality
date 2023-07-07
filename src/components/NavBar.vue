<script setup>
import { Icon } from '@iconify/vue';
import { ref } from 'vue'
import Button from './DynamicButton.vue'
import TrainingModal from './TrainingModal.vue'

const isModalOpen = ref(false)
const menuOpen = ref(false)

const closeModal = () => (isModalOpen.value = false)
</script>

<template>
  <nav>
    <div class="logo"><RouterLink to="/">Mamba Mentality</RouterLink></div>

    <div class="more">
      <div class="about"><RouterLink to="/about">About</RouterLink></div>
      <Button @click="isModalOpen = true">Improve My Game</Button>
    </div>

    <div class="mobile">
      <div class="hamburger" @click="menuOpen=!menuOpen">
        <Icon icon="streamline:interface-setting-menu-parallel-hamburger-square-navigation-parallel-hamburger-buttonmenu-square" />
      </div>
    </div>

    <div class="mobile-items" v-if="menuOpen">
        <div class="about"><RouterLink to="/about">About</RouterLink></div>
        <div>
        <Button @click="isModalOpen = true">Improve My Game</Button>
        </div>
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

  .mobile{
    display: none;
  }

  @media screen and (max-width: 650px) {
    .more{
    display: none;
    }

    .mobile{
      display: block;
      
      .hamburger{
        color: #fff;
        font-size: 1.8em;
        cursor: pointer;
      }
    }

    .mobile-items{
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 12px;
      position: absolute;
      top: 54px;
      right: 30px;
      width: 250px;
      background-color: black;
      border: 1px solid #fff;
      border-radius: 4px;
      padding: 15px 20px;

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
}
</style>

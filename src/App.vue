<script setup>
import { RouterView } from 'vue-router'
import Navigation from './components/NavBar.vue'
</script>

<template>
  <Navigation></Navigation>
  <RouterView />
</template>

<style>
@import './assets/main.css';
</style>

<script setup>
import Navigation from '../components/NavBar.vue'
import Button from '../components/DynamicButton.vue'
</script>

<template>
  <header>
    <Navigation></Navigation>

    <div class="text">
      <div class="slogan">Never let good enough <span class="green">be</span> enough!</div>
      <div class="caption">Curated videos and materials to take your game to the next level</div>

      <Button>Improve My Game</Button>
    </div>
  </header>
</template>

<style lang="scss" scoped>
header {
  height: 65vh;
  background: linear-gradient(0deg, rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)),
    url(https://ik.imagekit.io/Ochoja01/Mamba_Mentality/hero.png?updatedAt=1687364216670);
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  .text {
    color: #fff;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 80%;
    width: 90%;
    margin: auto;
    text-align: center;

    .slogan {
      font-size: 3em;
      margin-bottom: 5px;

      .green {
        color: var(--secondary-color);
      }
    }
    .caption {
      font-size: 1.2em;
      font-weight: 600;
      margin-bottom: 20px;
    }
  }
}
</style>

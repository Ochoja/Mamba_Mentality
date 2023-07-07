<script setup>
import Button from '../components/DynamicButton.vue'
</script>

<template>
  <div class="hero">
    <h1 class="heading">Mamba Mentality</h1>
    <div class="caption">A Learning Platform for Basketballers at all levels</div>
    <Button>Get Started</Button>
  </div>

  <section class="feature">
    <div>
      <h2>A Platform for all basketballers to learn</h2>
      <div class="caption">
        A platform for all basketballers to learn, grow and play Whether you are a beginner or a
        pro, you can find the resources you need Join us today and discover the joy of basketball!
      </div>
      <Button>Take Me There</Button>
    </div>
    <div class="img"></div>
  </section>

  <section class="feature">
    <div>
      <h2>TURN YOUR WEAKNESSES INTO STRENGTH</h2>
      <div class="caption">
        Elevate your game by focusing on your weaknesses and become a well-rounded basketball
        player. Improve on areas that are lacking and become a complete player
      </div>
      <Button>Elevate your Game</Button>
    </div>
    <div class="img"></div>
  </section>
</template>

<style lang="scss" scoped>
.hero {
  height: 65vh;
  background: linear-gradient(0deg, rgba(0, 0, 0, 0.6) 0%, rgba(0, 0, 0, 0.6) 100%),
    url(https://ik.imagekit.io/Ochoja01/Mamba_Mentality/hero2.png?updatedAt=1688683898154),
    lightgray 50% / cover no-repeat;
  background-position: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: #fff;

  .heading {
    font-size: 4em;
    font-weight: 700;
  }

  .caption {
    font-weight: 700;
    font-size: 1.25em;
    margin-bottom: 20px;
  }
}
</style>

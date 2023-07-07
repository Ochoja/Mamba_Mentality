<script setup>
import Button from '../components/DynamicButton.vue'
</script>

<template>
  <div class="hero">
    <h1 class="heading">Mamba Mentality</h1>
    <div class="caption">A Learning Platform for Basketballers at all levels</div>
    <Button route="/">Get Started</Button>
  </div>

  <section class="feature">
    <div class="text">
      <h2>A Platform for all basketballers to learn</h2>
      <div class="caption">
        A platform for all basketballers to learn, grow and play Whether you are a beginner or a
        pro, you can find the resources you need Join us today and discover the joy of basketball!
      </div>
      <div>
        <Button route="/">Take Me There</Button>
      </div>
    </div>
    <div class="img">
      <img
        src="https://ik.imagekit.io/Ochoja01/Mamba_Mentality/pexels-pixabay-267761__1_.jpg?updatedAt=1688686113575"
        alt=""
      />
    </div>
  </section>

  <section class="feature second">
    <div class="img">
      <img
        src="https://ik.imagekit.io/Ochoja01/Mamba_Mentality/pexels-pnw-production-8979932__1_.jpg?updatedAt=1688686117758"
        alt=""
      />
    </div>
    <div class="text">
      <h2>TURN YOUR WEAKNESSES INTO STRENGTH</h2>
      <div class="caption">
        Elevate your game by focusing on your weaknesses and become a well-rounded basketball
        player. Improve on areas that are lacking and become a complete player
      </div>
      <div>
        <Button route="/">Elevate your Game</Button>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.hero {
  height: 65vh;
  background: linear-gradient(0deg, rgba(0, 0, 0, 0.6) 0%, rgba(0, 0, 0, 0.6) 100%),
    url(https://ik.imagekit.io/Ochoja01/Mamba_Mentality/hero2.png?updatedAt=1688683898154),
    lightgray 50% / cover;
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

.feature {
  margin-top: 50px !important;
  width: 90%;
  margin: auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 150px;

  .text {
    display: flex;
    flex-direction: column;
    justify-content: center;

    h2 {
      font-size: 2.4em;
    }
    .caption {
      margin-bottom: 12px;
      font-size: 1.2em;
    }
  }

  .img {
    height: 80vh;
    width: 100%;

    img {
      border-radius: 4px;
      height: inherit;
      width: 100%;
      object-fit: cover;
    }
  }
}

@media screen and (max-width: 980px) {
  .feature {
    gap: 60px;

    .img {
      height: 65vh;
    }
  }
}

@media screen and (max-width: 780px) {
  .feature {
    gap: 30px;
    grid-template-columns: 1fr;

    .img {
      height: 75vh;
      grid-row: 2;
    }
  }
}
</style>

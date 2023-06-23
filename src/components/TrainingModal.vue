<script setup>
import Button from '../components/DynamicButton.vue'
// import { Icon } from '@iconify/vue'
</script>

<template>
  <div class="background">
    <div class="popup">
      <div class="heading">
        <h2>Personalize Training</h2>
        <p>Choose skill level and area you wish to improve on</p>
      </div>


      <h3>Skill Level</h3>
      <div class="items">
        <div class="skill">
          <div class="text">Beginner</div>
          <div class="icons"></div>
        </div>

        <div class="skill">
          <div class="text">Intermediate</div>
          <div class="icons"></div>
        </div>

        <div class="skill">
          <div class="text">Advanced</div>
          <div class="icons"></div>
        </div>
      </div>

      <h3>Area of Focus</h3>
      <div class="items">
        <div class="skill">
          <div class="text">Shooting</div>
          <div class="icon"></div>
        </div>

        <div class="skill">
          <div class="text">Dribbling</div>
          <div class="icon"></div>
        </div>

        <div class="skill">
          <div class="text">Passing</div>
          <div class="icon"></div>
        </div>

        <div class="skill">
          <div class="text">Finishing</div>
          <div class="icon"></div>
        </div>
      </div>

      <div class="buttons">
        <Button>Get Training</Button>
        <Button type="danger">Clear Selection</Button>
      </div>
    </div>
  </div>
</template>


<style lang="scss" scoped>
  .background{
    position: fixed;
    top: 0;
    left: 0;
    height: 100vh;
    width: 100%;
    background: rgba($color: #000000, $alpha: 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
    overflow-y: auto;

    .popup{
      background: #fff;
      padding: 30px;
      max-width: 95%;
      border-radius: 4px;

      .heading{
        margin-bottom: 30px;
      }

      .buttons{
        display: flex;
        gap: 12px;
      }

      h3{
        margin-bottom: 4px;
      }

      .items{
        display: flex;
        gap: 20px;
        margin-bottom: 25px;

        .skill{
          border: 0.5px solid var(--secondary-color);
          padding: 8px;
          border-radius: 4px;
          .text{
            font-weight: 500;
          }
        }
      }
    }
  }
</style>
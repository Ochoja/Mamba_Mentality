<script setup>
import Button from '../components/DynamicButton.vue'
import { Icon } from '@iconify/vue'

const levels = [
  { id: 1, skill: 'Beginner', active: false },
  { id: 2, skill: 'Intermediate', active: false },
  { id: 3, skill: 'Advanced', active: false }
]

function toggleActive(array, id) {
  let arr = eval(array)
  arr[id].active = !arr[id].active
  console.log(arr[id].active)
}
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
        <div
          :class="{ skill: true, active: level.active }"
          v-for="level in levels"
          :key="level.id"
          @click="toggleActive('levels', level.id)"
        >
          <div class="text">{{ level.skill }}</div>
          <div class="icons">
            <Icon icon="material-symbols:star" v-for="icon in level.id" :key="icon" />
          </div>
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
.background {
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

  .popup {
    background: #fff;
    padding: 30px;
    max-width: 95%;
    border-radius: 4px;

    .heading {
      margin-bottom: 30px;
    }

    .buttons {
      display: flex;
      gap: 12px;
    }

    h3 {
      margin-bottom: 4px;
    }

    .items {
      display: flex;
      gap: 20px;
      margin-bottom: 25px;

      .skill {
        border: 0.5px solid var(--secondary-color);
        padding: 8px 16px;
        border-radius: 4px;
        cursor: pointer;
        .text {
          font-weight: 500;
          text-align: center;
        }

        .icons {
          display: flex;
          gap: 3px;
          justify-content: center;
          font-size: 1.4em;
          color: var(--secondary-color);
        }
      }

      .skill.active {
        background: var(--secondary-color);
        border: 2px solid #000;

        .text {
          font-weight: 700;
        }

        .icons {
          color: #000;
        }
      }
    }
  }
}
</style>

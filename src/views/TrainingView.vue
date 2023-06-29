<script setup>
import { onMounted, ref, watch } from "vue";
import { useRoute } from "vue-router";
import axios from 'axios'

const route = useRoute()
const query = route.params.query
const title = ref(query.replaceAll('+', ' ')) //page title
const videos = ref([])
const endpoint = 'https://www.googleapis.com/youtube/v3/search'
const api_key = 'AIzaSyBIdZRCaifV3zjSALQXvYmBFPyf4BPpaYE'
const final_query = `${endpoint}?key=${api_key}&type=video&part=snippet&maxResults=10&q=${query}+basketball`

// change title when route is updated
watch(route, () => {
  title.value = query.replaceAll('+', ' ')
  getTraining()
})

async function getTraining() {
  try {
    const response = await axios.get(final_query)
    console.log(response.data)

    // Filter results
    for (const item of response.data.items) {
      const video = {}
      video.id = item.id.videoId
      video.title = item.snippet.title
      videos.value.push(video) // add result to videos array
    }
  } catch (error) {
    console.log(error)
  }
}

onMounted(() => {
  getTraining()
})

</script>

<template>
  <div class="trainings">
    <h1>{{ title }}</h1>
  </div>

  <div class="videos">
    {{ videos }}
  </div>
</template>

<style lang="scss" scoped>
  h1{
    text-align: center;
    margin-top: 30px;
  }
</style>

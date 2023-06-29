<script setup>
import { onMounted, ref, watch } from 'vue'
import { useRoute } from 'vue-router'
import axios from 'axios'

const route = useRoute()
const query = ref(route.params.query)
const title = ref(query.value.replaceAll('+', ' ')) //page title
const videos = ref([])

// change title when route is updated
watch(
  () => route.params.query,
  () => {
    videos.value = []
    getTraining(route.params.query)
    console.log('fIRED')
    title.value = route.params.query.replaceAll('+', ' ')
  }
)

// watch(
//   () => route.params.query,
//   (to, from) => {
//     videos.value = []
//     title.value = query.value.replaceAll('+', ' ')
//     console.log(videos)
//     getTraining()
//   }
// )

async function getTraining(search_query) {
  const endpoint = 'https://www.googleapis.com/youtube/v3/search'
  const api_key = 'AIzaSyC4-q_uDSIJLFzNaGuKPmZBGFg74LY-tJg'
  const final_query = `${endpoint}?key=${api_key}&type=video&part=snippet&maxResults=10&q=${search_query}+basketball`

  try {
    const response = await axios.get(final_query)
    let count = 1
    // Filter results
    for (const item of response.data.items) {
      const video = {}
      video.id = item.id.videoId
      video.title = item.snippet.title
      video.key = count
      videos.value.push(video) // add result to videos array
      count++
    }
  } catch (error) {
    console.log(error)
  }
}

onMounted(() => {
  getTraining(route.params.query)
})
</script>

<template>
  <div class="trainings">
    <h1>{{ title }}</h1>
  </div>

  <div class="videos">
    <div v-for="video in videos" :key="video.key" class="video">
      <iframe :src="`https://www.youtube.com/embed/${video.id}`" frameborder="0" allowfullscreen></iframe>
    </div>
  </div>
</template>


<style lang="scss" scoped>
h1 {
  text-align: center;
  margin: 40px auto 20px auto;
}

.videos {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  width: 80%;
  margin: auto;

  .video {
    position: relative;
    padding-bottom: 56.25%;
    height: 0;
    max-width: 500px;
  }

  .video iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
}
</style>

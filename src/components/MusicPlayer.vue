<script setup lang="ts">
import { ref } from 'vue'
import { onMounted, onUnmounted } from 'vue'
import { useRoute } from 'vue-router'
import { RouterLink } from 'vue-router'

const audio = ref(null as null | HTMLAudioElement)

onMounted(() => {
  audio.value = document.querySelector('audio')
  console.log(audio)
})
onUnmounted(() => {
  audio.value = null
})

const changePlayStatu = () => {
  if (audio.value == null) {
    return
  }
  if (audio.value.paused) {
    audio.value.play()
  } else {
    audio.value.pause()
  }
}

const route = useRoute()
</script>

<template>
  <div id="control">
    <img :src="import.meta.env.VITE_LRC_URL" alt="专辑图片" />
    <RouterLink to="/select" v-if="route.path == '/'">Q</RouterLink>
    <RouterLink to="/" v-if="route.path == '/select'">#</RouterLink>
    <button :onclick="changePlayStatu">| |</button>
    <button>></button>
    <div id="lrc">歌词</div>
  </div>
  <audio :src="import.meta.env.VITE_MUSIC_URL"></audio>
</template>

<style scoped>
#control {
  width: 100%;
  height: 100%;
  display: grid;
  gap: 0.5em;
  grid-template-columns: repeat(4, 2em) 1fr;
}

img {
  width: 2em;
  height: 2em;
  display: block;
  border-radius: 4px;
}

a {
  display: block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  text-align: center;
  color: unset;
  text-decoration: unset;
}

#lrc {
  line-height: 2em;
  padding-left: 0.5em;
}
</style>

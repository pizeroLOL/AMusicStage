<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import MusicPlayer from './components/MusicPlayer.vue'
</script>

<template>
  <!-- <header>
    <nav>
      <RouterLink to="/">播放列表</RouterLink>
      <RouterLink to="/select">点歌台</RouterLink>
    </nav>
  </header> -->

  <main>
    <RouterView />
  </main>

  <footer>
    <MusicPlayer />
  </footer>
</template>

<style scoped>
header {
  padding: 0.5em 0;
  background-color: var(--md-sys-color-surface-1);
}

nav {
  text-align: center;
}

nav a {
  flex: 1;
  color: unset;
  text-decoration: unset;
  display: inline-block;
  background-color: var(--md-sys-color-surface-3);
  margin-right: 1em;
  padding: 0.25em 0.5em;
  border-radius: 0.5em;
}

nav a:hover {
  background-color: var(--md-sys-color-surface-variant);
}

main {
  padding-bottom: 3em;
}

footer {
  width: 100dvw;
  height: 100dvh;
  position: fixed;
  bottom: 0;
  left: 0;
  height: 2em;
  padding: 0.5em;
  background-color: var(--md-sys-color-surface-3);
}
</style>

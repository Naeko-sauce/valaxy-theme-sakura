<script setup lang="ts">
import { usePostList } from 'valaxy'
import { ref } from 'vue'

const routes = usePostList()

const post = routes.value[0]

const config = ref({
  title: post.title,
  link: post.path,
  src: post.cover,
  excerpt: post.excerpt,
  date: post.date,
  target: '',
})

function configUpdate(newConfig: any) {
  config.value = newConfig
}
</script>

<template>
  <ArticleThemeMasonry
    :link="config.link" :date="config.date" :src="config.src"
    :title="config.title" :excerpt="config.excerpt" :target="config.target"
  />
  <CodeEditor :config="config" @update:config="configUpdate" />
</template>

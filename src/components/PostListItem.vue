<script setup lang="ts">
import type { BlogCategory } from '@/constants/blog'
import router from '@/router'

defineProps<{
  id: number
  title: string
  createdDate: number
  contentPreview: string
  category: BlogCategory
  totalComments: number
}>()

const onClickPost = (id: number) => {
  router.push(`/post/${id}`)
}
</script>

<template>
  <div>
    <img class="post-pict" />
    <div class="item-container">
      <h1 @click="onClickPost(id)">{{ title }}</h1>
      <div class="detail-container">
        <span class="created-date">{{ new Date(createdDate).toDateString() }}</span>
        <span class="category">{{ category }}</span>
        <span class="total-comment">{{ `${totalComments} comments` }}</span>
      </div>
      <p class="content-preview">{{ contentPreview }}</p>
      <RouterLink :to="`/post/${id}`">Read More ></RouterLink>
    </div>
  </div>
</template>

<style scoped>
h1 {
  cursor: pointer;
}
.detail-container span {
  margin-right: 8px;
}

.detail-container,
.content-preview {
  margin-bottom: 8px;
}
</style>

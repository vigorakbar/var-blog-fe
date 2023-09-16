<script setup lang="ts">
import { ref } from 'vue'
import { BlogCategory } from '@/constants/blog'
import PostListItem from '@/components/PostListItem.vue'

const blogList = ref([
  {
    id: 1,
    title: 'Post 1',
    createdDate: new Date().getTime(),
    contentPreview:
      'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Omnis possimus, laborum voluptatum nihil voluptas eius iste porro, consectetur praesentium corporis iusto vel non quae et ad molestiae veniam fugit? Labore.',
    category: BlogCategory.Travel,
    totalComments: 5
  },
  {
    id: 2,
    title: 'Post 2',
    createdDate: new Date().getTime(),
    contentPreview:
      'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Omnis possimus, laborum voluptatum nihil voluptas eius iste porro, consectetur praesentium corporis iusto vel non quae et ad molestiae veniam fugit? Labore.',
    category: BlogCategory.Personal,
    totalComments: 1
  },
  {
    id: 3,
    title: 'Post 3',
    createdDate: new Date().getTime(),
    contentPreview:
      'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Omnis possimus, laborum voluptatum nihil voluptas eius iste porro, consectetur praesentium corporis iusto vel non quae et ad molestiae veniam fugit? Labore.',
    category: BlogCategory.Tech,
    totalComments: 12
  }
])
</script>

<template>
  <main>
    <PostListItem v-for="item in blogList" :key="item.id" v-bind="item" />
  </main>
</template>

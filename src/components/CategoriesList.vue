<template>
  <forum-list
    v-for="category in categories"
    :key="category.id"
    :forums="getForumsForCategory(category)"
    :title="category.name"
    :categoryId="category.id"
  />
</template>

<script>
import ForumList from '@/components/ForumList.vue'
import sourceData from '@/data.json'

export default {
  components: { ForumList },
  props: {
    categories: {
      require: true,
      type: Array
    }
  },
  methods: {
    getForumsForCategory (category) {
      return sourceData.forums.filter(f => f.categoryId === category.id)
    }
  }
}
</script>

<style>

</style>

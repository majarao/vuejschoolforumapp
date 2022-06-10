<template>
  <forum-list
    :title="category.name"
    :forums="getForumsForCategory(category)"
    :categoryId="category.id"
  />
</template>

<script>
import ForumList from '@/components/ForumList.vue'
import sourceData from '@/data.json'

export default {
  components: { ForumList },
  props: {
    id: {
      require: true,
      type: String
    }
  },
  computed: {
    category () {
      return sourceData.categories.find(c => c.id === this.id)
    }
  },
  methods: {
    getForumsForCategory () {
      return sourceData.forums.filter(f => f.categoryId === this.id)
    }
  }
}
</script>

<style>

</style>

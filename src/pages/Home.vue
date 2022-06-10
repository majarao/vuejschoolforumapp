<template>
  <category-list :categories="categories"/>
</template>

<script>
import CategoryList from '@/components/CategoriesList.vue'
import sourceData from '@/data.json'

export default {
  data () {
    return {
      categories: sourceData.categories
    }
  },
  components: {
    CategoryList
  }
}
</script>

<style>

</style>

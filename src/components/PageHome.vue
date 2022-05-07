<template>
  <thread-list :threads="threads"/>
</template>

<script>
import ThreadList from '@/components/ThreadList.vue'
import sourceData from '@/data.json'

export default {
  data () {
    return {
      threads: sourceData.threads
    }
  },
  components: {
    ThreadList
  }
}
</script>

<style>

</style>

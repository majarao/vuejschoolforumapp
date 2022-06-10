<template>
  <div class="col-full push-top">
    <div class="forum-header">
      <div class="forum-details">
        <h1>{{ forum.name }}</h1>
        <p class="text-lead">{{ forum.description }}</p>
      </div>
      <a href="new-thread.html" class="btn-green btn-small">Start a thread</a>
    </div>
  </div>
  <div class="col-full push-top">
    <thread-list :threads="threads"/>
  </div>
</template>

<script>
import ThreadList from '@/components/ThreadList.vue'
import sourceData from '@/data.json'

export default {
  components: {
    ThreadList
  },
  props: {
    id: {
      require: true,
      type: String
    }
  },
  computed: {
    forum () {
      return sourceData.forums.find(f => f.id === this.id)
    },
    threads () {
      return sourceData.threads.filter(t => t.forumId === this.id)
    }
  }
}
</script>

<style>

</style>

<template>
  <div class="post-list">
    <div v-for="post in posts" :key="post.id" class="post">
      <div class="user-info">
        <a href="#" class="user-name">{{ userById(post.userId).name }}</a>
        <a href="#">
          <img class="avatar-large" :src="userById(post.userId).avatar" alt=""/>
        </a>
        <p class="desktop-only text-small">{{ postsByUser(post.userId) }} posts</p>
      </div>
      <div class="post-content">
        <div>
          <p>
            {{ post.text }}
          </p>
        </div>
      </div>
      <div class="post-date text-faded">
        <app-date :timestamp="post.publishedAt"/>
      </div>
    </div>
  </div>
</template>

<script>
import sourceData from '@/data.json'

export default {
  data () {
    return {
      users: sourceData.users,
      postByUser: sourceData.posts
    }
  },
  props: {
    posts: {
      require: true,
      type: Array
    }
  },
  methods: {
    userById (userId) {
      return this.users.find(u => u.id === userId)
    },
    postsByUser (userId) {
      return this.postByUser.filter(p => p.userId === userId).length
    }
  }
}
</script>

<style>

</style>

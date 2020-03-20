<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <div class="text-center">
          <div>
            <ul>
              <li v-for="post in posts.data" :key="post.id">
                {{ post.id }} {{ post.title }} {{ post.body }}
              </li>
            </ul>
          </div>
        <post-list />
      </div>
    </v-flex>
  </v-layout>
</template>

<script>
import Logo from '@/components/Logo.vue'
import VuetifyLogo from '@/components/VuetifyLogo.vue'
import PostList from '@/components/PostList.vue'

import axios from 'axios'
let url = 'http://localhost:3000/api/v1/posts'

export default {
  asyncData({ params }) {
    return axios.get(url)
      .then((res) => {
        return { posts: res.data}
      })
      .catch((e) => {
        error({ statusCode: 404, message: 'ページが見つかりません' })
      })
  },
  components: {
    Logo,
    VuetifyLogo,
    PostList
  },
}
</script>

<style>
</style>
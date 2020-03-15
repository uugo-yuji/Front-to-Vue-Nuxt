<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <div class="text-center">
          <div>
            <v-btn @click="getMsg">Hello</v-btn>
            {{ msg }}
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

// let url = 'http://localhost/api/v1/posts'
export default {
data: () => ({
    msg: ''
  }),
  methods: {
    getMsg () {
      this.$axios.$get('/api/v1/hello').then(res => (this.msg = res.msg))
    }
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
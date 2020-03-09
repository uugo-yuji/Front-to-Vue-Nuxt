<template>
  <div class="post-list">
    <v-container class="my-5">

      <v-layout row wrap>
        <v-flex v-for="post in posts" :key="post.name">
          <v-card class="mx-auto card-type">
            <v-list-item>
              <v-list-item-avatar color="indigo">
                <v-icon>{{ post.icon }}</v-icon>
              </v-list-item-avatar>
              <v-list-item-content>
                <v-list-item-subtitle>{{ post.tab }}</v-list-item-subtitle>
                <v-list-item-title class="headline font-weight">{{ post.title }}</v-list-item-title>
                <v-btn text color="deep-purple accent-4" to="/PostShow">
                <v-list-item-subtitle>by {{ post.name }}</v-list-item-subtitle>
              </v-btn>
                <v-list-item-subtitle>{{ post.posttime }}</v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>

            <v-img src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg" height="194"></v-img>

            <v-card-text>
                <p class="font-weight">{{ post.text }}</p>
            </v-card-text>

            <v-card-actions>
              <v-btn text color="deep-purple accent-4" to="/PostShow">
                コメント
              </v-btn>
              <v-spacer></v-spacer>
              <v-btn icon>
                <v-icon>mdi-book</v-icon>
              </v-btn>
              <v-btn icon>
                <v-icon>mdi-share-variant</v-icon>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>

    </v-container>
  </div>
</template>

<script>

export default {
  data() {
    return {
      posts: [
        { name: 'user1', icon: 'mdi-account-circle', userphoto: '', posttime: '2020/01/01', title: 'title1', text: 'Visit ten places on our planet that are undergoing the biggest changes today.', tab: 'tab1'},
        { name: 'user2', icon: 'mdi-account-circle', userphoto: '', posttime: '2020/01/01', title: 'title2', text: 'Visit ten places on our planet that are undergoing the biggest changes today.', tab: 'tab2'},
        { name: 'user3', icon: 'mdi-account-circle', userphoto: '', posttime: '2020/01/01', title: 'title3', text: 'Visit ten places on our planet that are undergoing the biggest changes today.', tab: 'tab1'},
        { name: 'user4', icon: 'mdi-account-circle', userphoto: '', posttime: '2020/01/01', title: 'title4', text: 'Visit ten places on our planet that are undergoing the biggest changes today.', tab: 'tab2'},
      ]
    }
  }
}
</script>

<style>
.font-weight{
  font-weight: bold;
}

.card-type {
  max-width: 600px;
  margin-bottom: 10px;
}
</style>
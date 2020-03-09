<template>
  <v-app id="keep" class="pa">
    <v-app-bar app clipped-left color="primary" dark>
      <v-app-bar-nav-icon @click="drawer = !drawer" />
      <span class="title ml-3 mr-5">動画Q&Aサービス</span>
      <v-text-field solo-inverted flat hide-details label="検索" prepend-inner-icon="search"/>

      <v-spacer />
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" app clipped color="grey lighten-4">
      <v-list dense class="grey lighten-4">
        <template v-for="(item, i) in items">
          <v-row v-if="item.heading" :key="i" align="center">
            <v-col cols="6">
              <v-subheader v-if="item.heading">
                {{ item.heading }}
              </v-subheader>
            </v-col>
          </v-row>
          <v-divider v-else-if="item.divider" :key="i" dark class="my-4"/>
          <v-list-item v-else :key="i" link :to="item.url">
            <v-list-item-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title class="grey--text">
                {{ item.text }}
              </v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </template>
      </v-list>
    </v-navigation-drawer>
  </v-app>
</template>

<script>
  export default {
    props: {
      source: String,
    },
    data: () => ({
      drawer: null,
      items: [
        { heading: 'プロフィール' },
        { icon: 'mdi-account-circle', text: 'ユーザ名', url: '/profile' },
        { divider: true },
        { icon: 'mdi-border-color', text: 'あなたの投稿', url: '/profile/post' },
        { icon: 'mdi-book', text: 'ブックマーク', url: '/profile/bookmark' },
        { icon: 'fas fa-edit', text: 'カテゴリー', url: '/category' },
        { divider: true },
        { text: '概要', url: '/inspire' },
        { icon: 'settings', text: '設定', url: '/profile/setting' },
        { icon: 'help', text: 'ヘルプ', url: '/help' },
        { icon: 'exit_to_app', text: 'ログアウト' },
      ],
    }),
  }
</script>

<style>
#keep .v-navigation-drawer__border {
  display: none;
}
.pa {
  height: 80px;
}
</style>
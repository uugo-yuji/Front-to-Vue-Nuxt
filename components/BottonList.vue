<template>
<div id="app">
  <v-app id="inspire" class="pa">
    <v-bottom-navigation :value="activeBtn" grow color="primary">
      <v-btn to="/" nuxt>
        <span>ホーム</span>
        <v-icon>home</v-icon>
      </v-btn>
  
      <v-btn to="/PostFrom" nuxt>
        <span>投稿</span>
        <v-icon>mdi-border-color</v-icon>
      </v-btn>
  
      <v-btn to="/Profile" nuxt>
        <span>マイページ</span>
        <v-icon>mdi-account-circle</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </v-app>
</div>
</template>

<script>
export default {
    data () {
    return {
      activeBtn: 0,
    }
  }
}
</script>
<style>
pa {
  height: 80px;
}
</style>
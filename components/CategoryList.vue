
<template>
  <v-card class="mx-auto card-type">
    <v-list rounded>
      <v-subheader>カテゴリーリスト</v-subheader>
      <v-list-item-group>
        <v-list-item v-for="(item, i) in items" :key="i">
          <v-list-item-icon>
            <v-icon v-text="item.icon"></v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title v-text="item.text"></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-card>
</template>

<script>
  export default {
    data: () => ({
      items: [
        { text: '仮 生活', icon: 'mdi-clock' },
        { text: '仮 音楽', icon: 'mdi-account' },
        { text: '仮 アニメ', icon: 'mdi-flag' },
      ],
    }),
  }
</script>

<style scoped>
.card-type {
  width: 600px;
  margin-bottom: 10px;
}
</style>

<template>
  <v-app>
    <div>
      カテゴリー一覧（ここからも投稿を検索）
    </div>
      <category-list />
  </v-app>
</template>

<script>
import CategoryList from '@/components/CategoryList.vue'

export default {
  components: {
    CategoryList
  }
}
</script>
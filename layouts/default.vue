<template>
  <div>
    <Header />
    <Botton-list />
    <main>
      <nuxt />
    </main>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import BottonList from "@/components/BottonList.vue";

export default {
  components: {
    Header,
    BottonList
  }
}
</script>
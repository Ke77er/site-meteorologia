<template>
  <main-layout>
    <Comments />
  </main-layout>
</template>
<script>
  import MainLayout from '../layouts/Main.vue'
  import Comments from '../components/graficos/comments.vue'

  export default {
    components: {
      MainLayout,
      Comments
    }
  }
</script>

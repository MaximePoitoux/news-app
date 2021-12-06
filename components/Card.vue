<template>
  <div class="bg-gray-300 p-10">
    <p>{{ article.publishedAt }}</p>
    <p>{{ article.title }}</p>
    <p>{{ article.description }}</p>
    <p></p>
    <p></p>
  </div>
</template>

<script>
export default {
  props: {
    article: {
      type: [Object],
      default: () => {
        return {}
      },
    },
  },
}
</script>

<style scoped></style>

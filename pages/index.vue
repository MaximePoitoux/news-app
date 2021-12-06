<template>
  <div>
    <Card v-for="article in articles" :key="article.title" :article="article" />
  </div>
</template>

<script>
export default {
  async asyncData({ $axios, error }) {
    return await $axios
      .$get(
        'https://newsapi.org/v2/top-headlines?country=fr&pageSize=100&apiKey=005a93515fac4347beee2c4bf9365109'
      )
      .then((res) => {
        // console.log(res.articles)
        return { articles: res.articles }
      })
      .catch((e) => {
        error({ statusCode: 404, message: 'The data has not been loaded' })
      })
  },
}
</script>

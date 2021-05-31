<template>
  <c-box bg="gray.50">
    <c-flex justify-content="center" align-items="center">
      <c-image h="50px" :src="require('@/assets/deezer-logo.png')" />
      <c-heading
        ml="3"
        font-family="Roboto Slab"
        class="heading"
        font-size="4em"
      >
        Chart
      </c-heading>
    </c-flex>
    <c-text
      font-family="Roboto Slab"
      font-size="lg"
      color="gray.600"
      text-align="center"
    >
      simple api with Axios.
    </c-text>

    <c-box
      v-for="list in charts.tracks.data"
      :key="list.id"
      max-w="600px"
      mx="auto"
      bg="white"
    >
      <CardPlayer
        :position="list.position"
        :title="list.title"
        :artist="list.artist.name"
        :preview="list.preview"
        :cover="list.album.cover"
      />
    </c-box>
  </c-box>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const charts = await $axios.$get('https://api.deezer.com/chart')

    return { charts }
  },
}
</script>

<style scoped>
.heading {
  background: -webkit-linear-gradient(#fe5f75, #fc9842);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
</style>

<template>
  <c-flex
    justify-content="space-between"
    shadow="sm"
    my="5"
    border-color="gray.300"
  >
    <!-- No, Name -->
    <c-flex align="center">
      <c-flex mx="10">
        <c-text font-family="Roboto Slab" font-size="4xl">
          {{ position }}
        </c-text>
      </c-flex>
      <c-flex>
        <c-box>
          <c-text font-family="Roboto Slab" as="h2" font-size="2xl">
            {{ title }}
          </c-text>
          <c-text font-family="Roboto Slab" color="gray.500">
            {{ artist }}
          </c-text>
          <c-flex my="3">
            <audio controls>
              <source :src="preview" type="audio/mpeg" />
              Your browser does not support the audio element.
            </audio>
          </c-flex>
        </c-box>
      </c-flex>
    </c-flex>
    <!-- Image Cover -->
    <c-flex>
      <c-image min-w="150px" :src="cover" alt="" />
    </c-flex>
  </c-flex>
</template>

<script>
export default {
  props: {
    position: {
      type: Number,
      default: 0,
    },
    title: {
      type: String,
      default: 'What a song ?',
    },
    artist: {
      type: String,
      default: 'What a artist ?',
    },
    preview: {
      type: String,
      default: 'Where a preview ?',
    },
    cover: {
      type: String,
      default: 'No cover ?',
    },
  },
}
</script>

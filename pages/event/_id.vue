<template>
  <div>
    <h1>Event #{{ id }}</h1>
  </div>
</template>
<script>
export default {
  // head() is used by vue-meta which is included with nuxt.
  head() {
    return {
      title: 'Event #' + this.id,
      meta: [
        {
          hid: 'hid description',
          name: 'name description',
          content: 'What you need to know about event #' + this.id
        }
      ]
    }
  },
  computed: {
    id() {
      return this.$route.params.id
    }
  }
}
</script>

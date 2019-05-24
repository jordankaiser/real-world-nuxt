<template>
  <div>
    <h1>{{ event.title }}</h1>
  </div>
</template>
<script>
import EventService from '@/services/EventService.js'
export default {
  // head() is used by vue-meta which is included with nuxt.
  head() {
    return {
      title: this.event.title,
      meta: [
        {
          hid: 'hid description',
          name: 'name description',
          content: 'What you need to know about ' + this.event.title
        }
      ]
    }
  },
  // asyncData is a nuxt function used to fetch data and pre-render it on the server. The response from this is merged into the vue data.
  async asyncData({ error, params }) {
    try {
      const { data } = await EventService.getEvent(params.id)
      return {
        event: data
      }
    } catch (e) {
      error({
        statusCode: 503,
        message: 'error message'
      })
    }
  }
}
</script>

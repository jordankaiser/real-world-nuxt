<template>
  <div>
    <h1>Events</h1>
    <EventCard
      v-for="(event, index) in events"
      :key="index"
      :event="event"
      data-index="index"
    />
  </div>
</template>
<script>
import EventCard from '@/components/EventCard.vue'
import EventService from '@/services/EventService.js'
export default {
  // head() is used by vue-meta which is included with nuxt.
  head() {
    return {
      title: 'Index title'
    }
  },
  // asyncData is a nuxt function used to fetch data and pre-render it on the server. The response from this is merged into the vue data.
  async asyncData({ error }) {
    try {
      const { data } = await EventService.getEvents()
      return {
        events: data
      }
    } catch (e) {
      error({
        statusCode: 503,
        message: 'error message'
      })
    }
  },
  components: {
    EventCard
  }
}
</script>

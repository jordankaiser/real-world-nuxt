<template>
  <div>
    <h1>Create an Event</h1>
  </div>
</template>
<script>
export default {
  // head() is used by vue-meta which is included with nuxt.
  head() {
    return {
      title: 'Create title',
      meta: [
        {
          hid: 'hid description',
          name: 'name description',
          content:
            'Donec nec nisi vitae felis facilisis dictum at vulputate sapien. Maecenas elementum arcu at leo sagittis, sed ultrices massa maximus.'
        }
      ]
    }
  }
}
</script>

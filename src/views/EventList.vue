<template>
  <div>
    <h1>Event listing</h1>

    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<script>
import EventCard from '@/components/EventCard'
import EventService from '@/services/EventService'

export default {
  name: 'EventList',
  components: { EventCard },
  data() {
    return {
      events: [],
    }
  },
  created() {
    EventService.getEvents()
      .then((response) => {
        this.events = response.data
      })
      .catch((error) => {
        console.log(error)
      })
  },
}
</script>

<style scoped></style>

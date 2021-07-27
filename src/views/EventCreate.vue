<template>
  <div>
    <h1>Event create, {{ user.name }}</h1>
    <p>This event was create by {{ user.id }}</p>
    <p>There are {{ callLength }} categories:</p>
    <ul>
      <li v-for="cat in categories" :key="cat">{{ cat }}</li>
    </ul>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'EventCreate',
  computed: {
    callLength() {
      return this.$store.getters.callLength
    },
    ...mapState(['user', 'categories']),
  },
}
</script>

<style scoped></style>

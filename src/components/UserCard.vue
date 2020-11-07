<template>
  <li>
    <h2>{{ name }}</h2>
    <button @click="showData">Show Details</button>
    <ul v-if="isShown">
      <li><strong>Phone:</strong> {{ phone }}</li>
      <li><strong>Email:</strong> {{ email }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  name: 'User Card',
  props: {
    name: String,
    phone: String,
    email: String
  },
  data () {
    return {
      isShown: false
    }
  },
  methods: {
    showData () {
      this.isShown = !this.isShown
    }
  }
}
</script>
<style lang="css" scoped>
ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
li {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

</style>

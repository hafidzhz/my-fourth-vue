<template>
  <li>
    <h2><p>{{ name }}</p> <p v-if="isFavorite">Favorited</p></h2>
    <button @click="showData">Show Details</button>
    <button @click="setFavorite">Set Favorite</button>
    <button @click="deleteData">Delete</button>
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
    id: String,
    name: String,
    phone: String,
    email: String,
    favorite: Boolean
  },
  data () {
    return {
      isShown: false,
      isFavorite: false
    }
  },
  methods: {
    showData () {
      this.isShown = !this.isShown
    },
    setFavorite () {
      this.isFavorite = !this.isFavorite
      this.$emit('toogle-favorite', this.id, this.isFavorite)
    },
    deleteData () {
      this.$emit('delete-data', this.id)
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
  margin: 1rem auto;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

</style>

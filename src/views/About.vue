<template>
   <section id="app">
      <ul v-for="list in lists" :key="list.id">
        <UserCard v-bind:name="list.name" v-bind:phone="list.phone" v-bind:email="list.email" />
      </ul>
    </section>
</template>

<script>
import UserCard from '@/components/UserCard.vue'

export default {
  components: {
    UserCard
  },
  data () {
    return {
      lists: [
        {
          id: 1,
          name: 'Name 1',
          phone: '1234567890',
          email: 'email@email'
        },
        {
          id: 2,
          name: 'Name 2',
          phone: '2234567890',
          email: 'email@email'
        },
        {
          id: 3,
          name: 'Name 3',
          phone: '2234567890',
          email: 'email@email'
        },
        {
          id: 4,
          name: 'Name 4',
          phone: '2234567890',
          email: 'email@email'
        },
        {
          id: 5,
          name: 'Name 5',
          phone: '1234567890',
          email: 'email@email'
        }
      ]
    }
  },
  methods: {
    showData () {

    }
  }
}
</script>

<style lang="css" scoped>
#app ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

#app li {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

#app h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #58004d;
  margin: 0 0 1rem 0;
}

#app button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background-color: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}

#app button:hover,
#app button:active {
  background-color: #ec3169;
  border-color: #ec3169;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}

</style>

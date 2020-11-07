<template>
  <section>
    <UserForm @add-contact="addContact" />
  </section>
  <section id="app">
    <ul>
      <UserCard
        v-for="list in lists" :key="list.id"
        v-bind:name="list.name"
        v-bind:phone="list.phone"
        v-bind:email="list.email"
        v-bind:id="list.id"
        @toogle-favorite="toogleFavorite"
        @delete-data="deleteData"
      />
    </ul>
  </section>
</template>

<script>
import UserCard from '@/components/UserCard.vue'
import UserForm from '@/components/UserForm.vue'

export default {
  components: {
    UserCard,
    UserForm
  },
  data () {
    return {
      lists: [
        {
          id: 1,
          name: 'Name 1',
          phone: '1234567890',
          email: 'email@email',
          isFavorited: false
        },
        {
          id: 2,
          name: 'Name 2',
          phone: '2234567890',
          email: 'email@email',
          isFavorited: false
        },
        {
          id: 3,
          name: 'Name 3',
          phone: '2234567890',
          email: 'email@email',
          isFavorited: false
        },
        {
          id: 4,
          name: 'Name 4',
          phone: '2234567890',
          email: 'email@email',
          isFavorited: false
        },
        {
          id: 5,
          name: 'Name 5',
          phone: '1234567890',
          email: 'email@email',
          isFavorited: false
        }
      ]
    }
  },
  methods: {
    toogleFavorite (id, favorite) {
      this.lists = this.lists.map(list => {
        if (list.id === id) {
          list.isFavorited = favorite
        } else {
          list.isFavorited = false
        }
        return list
      })
      console.log(this.lists)
    },
    addContact (name, phone, email) {
      const id = new Date().toISOString()
      const newContact = { id, name, phone, email }
      console.log(newContact)
      this.lists.push(newContact)
    },
    deleteData (id) {
      const newList = this.lists.filter(list => list.id !== id)
      this.lists = newList
    }
  }
}
</script>

<style lang="css" scoped>

section {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

section ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

section h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #58004d;
  margin: 0 0 1rem 0;
}

section button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background-color: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}

section button:hover,
section button:active {
  background-color: #ec3169;
  border-color: #ec3169;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}

</style>

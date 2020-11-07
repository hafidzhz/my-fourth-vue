<template>
  <form @submit.prevent="submitData">
    <label>Name</label>
    <input type="text" v-model="enteredName">
    <br>
    <label>Phone</label>
    <input type="text" v-model="enteredPhone">
    <br>
    <label>Email</label>
    <input type="text" v-model="enteredEmail">
    <br>
    <button>Submit</button>
  </form>
</template>

<script>
export default {
  data () {
    return {
      enteredName: '',
      enteredPhone: '',
      enteredEmail: ''
    }
  },
  methods: {
    submitData () {
      this.$emit('add-contact', this.enteredName, this.enteredPhone, this.enteredEmail)
    }
  },
  emit: ['add-contact']
}
</script>

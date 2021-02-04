<template>
  <div>
    <form @submit.prevent="addItem">
      <input type="text" v-model="msg" name="title" placeholder="Add things todo">
      <input type="submit" value="Submit" class="add" >
    </form>
  </div>
</template>

<script>
import { v4 as uuid } from 'uuid'
export default {
  name: 'AddItem',
  data () {
    return {
      msg: ''
    }
  },
  methods: {
    addItem () {
      // e.preventDefault()
      const item = {
        number: uuid(),
        msg: this.msg,
        isCompleted: false
      }
      this.$emit('add-todo', item)
      this.msg = ''
    }
  }
}
</script>

<style scoped>

</style>

<template>
  <div>
    <div v-for="(todo,index) in todos" :key="todo.title">
      <b-field class="is-pulled-left">
        <b-checkbox size="is-large">{{ todo.title }}</b-checkbox>
      </b-field>
      <a class="delete is-pulled-right" @click="remove(index)"></a>
      <div class="is-clearfix"></div>

    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  computed: {
    ...mapGetters(['todos'])
  },
  methods: {
    remove (index) {
      this.$delete(this.todos, index)
    }
  }
}
</script>

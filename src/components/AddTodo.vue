<template>
  <div>
      <form @submit.prevent="addTodo">
          <input type="text" v-model="title" name="title" placeholder="Whats up dog?...">
          <input type="submit" value="submit" class="btn">
      </form>
  </div>
</template>

<script>
export default {
    name: "AddTodo",
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            const newTodo = {
                title: this.title,
                completed: false 
            }
            // sen up to parent
            this.$emit('add-todo', newTodo);

            this.title = '';
        }
    }
}
</script>

<style scoped>
form {
    display: flex; 
    justify-content: center;
    }
</style>
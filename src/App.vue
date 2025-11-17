<script>
import Todo from "./components/Todo.vue";
export default {
  components: {
    Todo,
  },
  data() {
    return {
      nom: "",
      hiding: false,
    };
  },
  methods: {
    submit() {
      this.hiding = true;
    },
  },
};
</script>

<template>
  <div>
    <h1 class="m-2 text-center text-5xl text-red-700">Veille todoList</h1>
    <h4 class="nameForm mt-5" v-if="hiding === false">
      Bonjour:
      <input
        @keyup.enter="submit"
        class="border-none outline-none"
        v-model="nom"
        type="text"
        placeholder="Votre nom"
      />
    </h4>
    <h4 v-else class="text-info text-center text-3xl">Bonjour {{ nom }}</h4>
    <Todo />
  </div>
</template>

<style scoped>
.nameForm {
  text-align: center;
  font-size: 1.2rem;
  font-weight: bold;
}
</style>

<script>
import Todo from "./components/Todo.vue";
import Theme from "./components/Theme.vue";
export default {
  components: {
    Todo,
    Theme,
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
    <div class="flex justify-between px-3">
      <div></div>
      <h1 class="m-2 text-center text-5xl text-red-700">Veille todoList</h1>
      <Theme class="self-center" />
    </div>
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

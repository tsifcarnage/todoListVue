<script>
import Todo from "./components/Todo.vue";
import Themes from "./components/Themes.vue";
import { capitalize } from "vue";
export default {
  components: {
    Todo,
    Themes,
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
    capitalize(str) {
      if (str.length === 0) return str;
      return str.charAt(0).toUpperCase() + str.slice(1).toLowerCase();
    },
  },
};
</script>

<template>
  <div>
    <div class="flex flex-wrap justify-between px-3">
      <div></div>
      <h1 class="m-2 text-center text-5xl text-red-700">Veille todoList</h1>
      <Themes class="self-center phone" />
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
    <h4 v-else class="text-info text-center text-3xl">
      Bonjour {{ capitalize(nom) }}
    </h4>
    <Todo :capitalize="capitalize" />
  </div>
</template>

<style scoped>
@media (max-width: 418px) {
  .phone {
    margin: auto;
  }
}
.nameForm {
  text-align: center;
  font-size: 1.2rem;
  font-weight: bold;
}
</style>

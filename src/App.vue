<script>
import HelloWorld from "./components/todoList.vue";
export default {
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
    <h4 class="nameForm" v-if="hiding === false">
      Bonjour:
      <input
        @keyup.enter="submit"
        class="border-none outline-none"
        v-model="nom"
        type="text"
        placeholder="Votre nom"
      />
    </h4>
    <h4 v-else class="text-green-800 text-center text-3xl">
      Bonjour {{ nom }}
    </h4>
  </div>
</template>

<style scoped>
.nameForm {
  text-align: center;
  font-size: 1.2rem;
}
</style>

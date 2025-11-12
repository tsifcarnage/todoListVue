<script>
import HelloWorld from "./components/todoList.vue";
export default {
  data() {
    return {
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
    <h4>
      Bonjour:
      <input
        @keyup.enter="submit"
        class="border-none outline-none"
        id="nom"
        type="text"
        placeholder="Votre nom"
      />
    </h4>
  </div>
</template>

<style scoped></style>

<template>
  <div class="border-2 border-accent max-w-lg p-3 m-auto my-[10%]">
    <h2 class="text-center">Tache à faire</h2>
    <form class="flex flex-col gap-5" @submit.prevent="addUser">
      <label class="italic text-lg" for="tache"
        >Entrez la tache ci dessous:</label
      >
      <input
        class="p-2"
        v-model="add"
        type="text"
        name="tache"
        placeholder="Nouvelle tache"
        required
      />
      <button class="btn btn-accent" type="submit">Ajouter</button>
    </form>
    <ul
      class="bg-base-200 my-2 p-2 flex justify-between gap-2 text-center text-lg"
      v-for="(task, index) in tasks"
      :key="index"
    >
      <li class="self-center">$ {{ task }}</li>
      <button @click="delUser(index)" class="btn btn-error">Supprimer</button>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      add: "",
      tasks: [],
    };
  },
  methods: {
    addUser() {
      this.tasks.push(this.add);
      this.add = "";
    },
    delUser(index) {
      this.tasks = this.tasks.filter((_, taskid) => taskid != index);
      this.add = "";
    },
  },
};
</script>

<style>
h2 {
  font-size: 1.5rem;
  font-weight: bold;
}
</style>

<template>
  <div>
    <h2>Tache à faire</h2>
    <form @submit.prevent="addUser">
      <label for="tache">Entrez la tache</label>
      <input
        v-model="add"
        type="text"
        name="tache"
        placeholder="Nouvelle tache"
      />
      <button class="btn btn-accent" type="submit">Ajouter</button>
    </form>
    <p v-for="(task, index) in tasks" :key="index">{{ task }}</p>
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
  },
};
</script>

<style></style>

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
      <div class="flex flex-wrap gap-1">
        <button class="btn btn-accent flex-1" type="submit">Ajouter</button>
        <button @click="delAll()" class="btn btn-error flex-1" type="button">
          Tout supprimer
        </button>
      </div>
    </form>
    <ul v-for="(task, index) in tasks" :key="index">
      <section
        class="bg-base-200 my-2 p-2 flex justify-between gap-2 text-center text-lg"
        :class="{ 'bg-green-600 text-black': task.ending }"
      >
        <li class="self-center">$ {{ task.text }}</li>
        <div>
          <button
            v-if="task.ending"
            @click="backTask(index)"
            class="btn btn-warning mr-2"
          >
            Annuler
          </button>
          <button v-else @click="endTask(index)" class="btn btn-success mr-2">
            Tache fini
          </button>
          <button @click="delUser(index)" class="btn btn-error">
            Supprimer
          </button>
        </div>
      </section>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      add: "",
      tasks: [],
      ending: false,
    };
  },
  methods: {
    addUser() {
      this.tasks.push({
        text: this.add,
        ending: false,
      });
      this.add = "";
    },
    delUser(index) {
      this.tasks.splice(index, 1);
    },
    endTask(index) {
      this.tasks[index].ending = true;
    },
    backTask(index) {
      this.tasks[index].ending = false;
    },
    delAll() {
      this.tasks.splice(0, this.tasks.length);
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

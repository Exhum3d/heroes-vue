<template>
  <div class=" mt-6">
    <h1 class="text-4xl mb-24 text-center">
      There are {{ counter }} heroes in this list
    </h1>
    <div
      class="flex justify-between text-lg"
      v-for="(hero, index) in randomHeroes"
      :key="hero.name"
    >
      <p>{{ hero.name }}</p>
      <button
        class="bg-red-500 hover:bg-red-700 text-white text-lg font-bold px-4 py-2 mb-4 rounded w-10"
        @click="delHero(index)"
      >
        x
      </button>
    </div>
  </div>
  <form @submit.prevent="addNewHero()" class="mt-6  mx-auto">
    <div class="flex flex-col mb-4">
      <input
        class="border py-2 px-3 text-grey-darkest"
        type="text"
        v-model.trim="newHero"
        placeholder="Insert a new hero"
      />
    </div>
    <button
      class="block bg-blue-400 hover:bg-blue-800 text-white  text-lg mx-auto p-4 rounded"
      type="submit"
    >
      Add that Mofo
    </button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      newHero: "",
      randomHeroes: [
        { name: "Magneto" },
        { name: "El Luchador" },
        { name: "Deadpool" },
        { name: "Fish Man" },
        { name: "Wonder Slut" }
      ]
    };
  },
  methods: {
    addNewHero() {
      if (this.newHero !== "") {
        this.randomHeroes.unshift({ name: this.newHero });
        this.newHero = "";
      }
    },
    delHero(index) {
      this.randomHeroes = this.randomHeroes.filter((hero, i) => i != index);
    }
  },
  computed: {
    counter() {
      return this.randomHeroes.length;
    }
  }
};
</script>

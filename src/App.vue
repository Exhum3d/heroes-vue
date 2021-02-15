<template>
  <div class="flex h-screen  w-full bg-blue-200">
    <div class=" mx-auto w-1/3  bg-white rounded shadow-lg p-8 m-4">
      <RandomHeroesList />
    </div>
  </div>
</template>

<script>
//import AppHeader from "./components/AppHeader";
import RandomHeroesList from "./components/RandomHeroesList";

export default {
  components: { RandomHeroesList }
};
</script>

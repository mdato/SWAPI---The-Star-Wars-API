<template>
  <div id="app">
    <h3>{{ title }}</h3>
    <h6>{{ subtitle }}</h6>
    <div class="personajes col-md-12">
      <character v-for="(id, index) in initial_ids" :id="id" :key="index" />
    </div>
  </div>
</template>

<script>
import character from './components/Character.vue'

export default {
  name: 'app',
  data() {
    return {
      title: "SWAPI - The Star Wars API",
      subtitle: "Click on a character to generate a new one",
      initial_ids: [44, 63, 5]
    }
  },
  components: {
    character
  }
}
</script>

<style>
.personajes {
  margin: 0 auto;
  width: 100%;
  max-width: 1200px;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;
}

h6 {
  padding: 10px 0 20px 0;
}

.character-card {
  border: 2px solid rgb(41, 134, 246);
  padding: 20px;
}

@media only screen and (max-width: 576px) {
  .personajes {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 20px;
  }

  .character-card {
    width: 50vw;
    padding: 20px;
  }

}
</style>

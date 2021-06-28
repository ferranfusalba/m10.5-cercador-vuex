<template>
  <div>
    <div
      class="row"
      v-if="getInput.length >= 3 || getInput.length == 0"
      key="key"
    >
      <div class="card col-6 mb-2" v-for="item in getFilms" :key="item.id">
        <div
          v-if="item.available == true"
          class="card-header alert alert-success"
        >
          {{ item.title }}
          <p>Available: {{ item.available }}</p>
        </div>
        <div v-else class="card-header alert alert-danger">
          {{ item.title }}
          <p>Available: {{ item.available }}</p>
        </div>
        <div class="card-body">
          <p class="card-text">
            {{ item.description }}
          </p>
        </div>
      </div>
    </div>

    <div v-if="getFilms.length == 0" class="alert alert-danger">
      Ho sentim, no s'han trobat pel·lícules disponibles.
    </div>
    <div v-else-if="getInput.length >= 3 || getInput.length == 0"></div>
    <div v-else class="alert alert-info">
      Has de fer una cerca de mínim 3 caràcters.
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "Films",
  computed: {
    ...mapGetters(["getFilms", "getInput"]),
  },
};
</script>
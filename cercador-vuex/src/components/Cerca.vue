<template>
  <form>
    <div class="form-group">
      <input
        type="text"
        class="form-control"
        id="search"
        placeholder="Cerca"
        v-model="input"
        @input="checkInput(input)"
      />
    </div>
    <div class="form-check">
      <input
        type="radio"
        class="form-check-input"
        id="available"
        value="available"
        v-model="seleccionat"
        @input="changeAv(seleccionat)"
      />
      <label class="form-check-label" for="available">Disponible</label>
      <br />
      <input
        type="radio"
        class="form-check-input"
        id="notAvailable"
        value="notAvailable"
        v-model="seleccionat"
        @input="changeAv(seleccionat)"
      />
      <label class="form-check-label" for="notAvailable">No disponible</label>
      <br />
      <input
        type="radio"
        class="form-check-input"
        id="all"
        value="all"
        v-model="seleccionat"
        @input="changeAv(seleccionat)"
      />
      <label class="form-check-label" for="all">Totes les pel·lícules</label>
    </div>
  </form>
</template>

<script>
import { mapMutations } from "vuex";

export default {
  name: "Search",
  methods: { ...mapMutations(["checkInput", "changeAv"]) },
  computed: {
    input: {
      get() {
        return this.$store.state.input;
      },
      set(value) {
        this.$store.commit("checkInput", value);
      },
    },
    seleccionat: {
      get() {
        return this.$store.state.disp;
      },
      set(value) {
        this.$store.commit("changeAv", value);
      },
    },
  },
};
</script>
<template>
  <div id="computed-part-one">
    <h1>Guitarrist - {{ firstName }} {{ lastName }}</h1>
    <h1>Computed Property - Guitarrist {{ favGuitarrist }}</h1>

    <button @click="changeFavGuitarrist">Change Favorite Guitarrist</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstName: "Gustavo",
      lastName: "Cerati Martinez",
    };
  },
  methods: {
    changeFavGuitarrist() {
      this.favGuitarrist2 = "Cesc Vila";
    },
  },
  computed: {
    favGuitarrist() {
      return `${this.firstName} ${this.lastName}`;
    },
    favGuitarrist2: {
      get() {
        return `${this.firstName} ${this.lastName}`;
      },
      set(value) {
        const name = value.split(" ");
        this.firstName = name[0];
        this.lastName = name[1];
      },
    },
  },
};
</script>

<style></style>
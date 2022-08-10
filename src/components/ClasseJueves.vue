<template>
  <h1>
    hello my name is {{fullName()}}
  </h1>
</template>

<script>
export default {
  data() {
    return {
      firstName:'Paulo',
      lastName: 'Almeida'
    };
  },
  methods: {
    fullName(){
      return `${this.firstName} ${this.lastName}`
    }
  },
  computed: {},
  watch: {},
};
</script>
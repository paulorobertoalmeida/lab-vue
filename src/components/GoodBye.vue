<template>
  <div v-for="(post, index) in posts" :key="index">
    <h1>{{ post.name }}</h1>
    My age is {{ post.age }} <br />
    {{ post.comment }} <br />
    {{ injected }} <br />
    <span v-html="html"></span>
    {{ fruta }}

    <span
      v-if="post.age >= 21 && canDrink"
      :style="{ 'background-color': 'green', color: 'yellow' }"
    >
      De Acurdo con su edad tu Puedes beber 😎</span
    >
    <span v-else :style="{ 'background-color': 'red', color: 'white' }"
      >De acuerdo con su edad no puedes beber 😩</span
    >
    <br />
    <button @click="say('hi')">Say hi</button>
    <hr />

    <h1 v-for="(name, value) in names" :key="value"> {{value + 1}} : {{name.toUpperCase()}}</h1>
    
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      injected: "me encanta las manzanas",
      fruta: "naranja",
      showElement: true,
      names:['diego', 'jarko', 'alex'],
      posts: [
        {
          name: "Paulo",
          age: 35,
          comment: "Soy Brasileño y vivo en Barcelona desde 2018",
        },
        {
          name: "Ana",
          age: 16,
          comment: "Portuguesa y vive en Copenhagen desde 2020",
        },
        {
          name: "Luisa",
          age: 32,
          comment: "Francesa y vive en Bahamas desde 2008",
        },
      ],
      html: `<p>mi pelicula favorita es Vanilla Sky</p>`,
      canDrink: true,
      cantDrink: "No puede beber",
      count: 0,
    };
  },
  methods: {
    say(message) {
      alert(message);
    },
  },
};
</script>

<style>
</style>
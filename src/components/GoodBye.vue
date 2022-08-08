<template>
  <div v-for="(post, index) in posts" :key="index">
    <h1>{{ post.name }}</h1>
    My age is {{ post.age }} <br />
    {{ post.comment }} <br />
    {{ injected }} <br />
    <span v-html="html"></span>
    {{ fruta }}
    <br />
    <span v-if="post.age >= 21 && canDrink"> 'Puedo beber'</span>
    <span v-else>'No puedo beber'</span>

    <button @click="count++">count is: {{ count }}</button>


  </div>
</template>

<script>
export default {
  data() {
    return {
      injected: "me encanta las manzanas",
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
};
</script>

<style>
</style>
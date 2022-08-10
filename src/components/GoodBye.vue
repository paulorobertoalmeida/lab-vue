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

    <h1 v-for="(name, value) in names" :key="value">
      {{ value + 1 }} : {{ name.toUpperCase() }}
    </h1>

    <ul v-for="(band, index) in bands" :key="index">
      <li>
        {{ band.name }}
      </li>
      <li>{{ index + 1 }}: {{ band.name }} : {{ band.genre }}</li>
      <span
        v-if="band.genre == 'Heavy-metal'"
        :style="{ 'background-color': 'red', color: 'white' }"
      >
        {{ band.name }} heavy-metal</span
      >
      <span v-else> {{ band.name }} is not heavy</span>
    </ul>
    <hr />
    <ul v-for="(key, value, index) in gringo" :key="index">
      <li>{{ value }}</li>
    </ul>
  </div>

  <div v-for="(movie, value) in disney" :key="value">
    <h2>Movie {{ movie.title }} : {{ movie.year }} - {{ movie.year }}</h2>
    <p v-for="(actor, index) in movie.cast" :key="index">
      {{ index + 1 }} : {{ actor }}
    </p>
  </div>

  <p>{{ 3 + 5 }}</p>

  {{ sum(50, 50) }}

  <div id="methods">
    <div id="methods-part-1"></div>
    <div id="methods-part-2"></div>
    <h1>{{ nameEvent }}</h1>
    <button @click="nameEvent = 'Lebron James'">Click me to change name</button>
    <h2>{{ count }}</h2>
    <button @click="increment">plus</button>
    <button @click="count--">plus</button>

    <button @click="changeName">kamalakan</button>
    <hr />
    <h3>{{ countER }}</h3>
    <button @click="multiply">MULTIPLY * 2</button>
    <button @click="decrement">DECREMENT 15</button>
    <button @click="reset">RESET</button>
    <hr />

    {{ injected }}
    <button @click="injected = 'Melocoton'">Cambia de fruta</button>

    <hr />

    <div>
    <label for="name">Name</label>
    <input type="text" v-model="formValue.formName" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      injected: "me encanta las manzanas",
      fruta: "naranja",
      showElement: true,
      names: ["diego", "jarko", "alex"],
      nameEvent: "Michael Jordan",
      countER: 1,
      gringo: {
        name: "Thomas",
        country: "France",
        food: "croissant",
      },
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
      countPlus: 0,
      bands: [
        {
          name: "Metallica",
          genre: "Heavy-metal",
        },
        {
          name: "The Strokes",
          genre: "Garage",
        },
        {
          name: "Marvin Gaye",
          genre: "soul",
        },
        {
          name: "The Libertines",
          genre: "Garage",
        },
        {
          name: "Megadeth",
          genre: "Heavy-metal",
        },
      ],
      disney: [
        // ...
        {
          title: "Avengers: Age of Ultron",
          year: 2015,
          cast: [
            "Robert Downey, Jr.",
            "Chris Evans",
            "Chris Hemsworth",
            "Mark Ruffalo",
          ],
          genres: ["Action"],
        },
        // ...
        {
          title: "The Avengers",
          year: 2012,
          cast: [
            "Robert Downey, Jr.",
            "Chris Evans",
            "Mark Ruffalo",
            "Chris Hemsworth",
            "Scarlett Johansson",
            "Jeremy Renner",
            "Tom Hiddleston",
            "Clark Gregg",
            "Cobie Smulders",
            "Stellan Skarsgård",
            "Samuel L. Jackson",
          ],
          genres: ["Superhero"],
        },
      ],
      nameEve: "nada",
      formValue: {
        formName: "",
      }
    };
  },
  methods: {
    say(message) {
      alert(message);
    },
    sum(a, b) {
      return a + b;
    },
    increment() {
      this.count += 1;
    },
    multiply(event) {
      this.countER *= 2;
      console.log(event);
    },
    decrement(event) {
      this.countER -= 15;
      console.log(event);
    },
    display(data) {
      return data;
    },
    changeName(event) {
      this.nameEve = "Stunning Green";
      console.log(event);
    },
    reset() {
      this.countER *= 0;
    },
  },
};
</script>

<style>
</style>
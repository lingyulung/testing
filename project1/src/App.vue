<script>
export default {
  data() {
    return {
      count: 3,
      persons: [
        {
          id: 1,
          name: "Leon",
          age: 20,
        },
        {
          id: 2,
          name: "Alex",
          age: 24,
        },
        {
          id: 3,
          name: "Darren",
          age: 30,
        },
      ],
      newPerson: "",
      newAge: "",
    };
  },
  methods: {
    addPerson() {
      const people = {
        id: this.count + 1,
        name: this.newPerson,
        age: this.newAge,
      };

      this.persons.push(people);
    },
    removePerson(id) {
      console.log(id);
      // this.persons = this.persons.filter((person) => {
      //   person.id != id;
      // });
      this.persons.splice(id - 1, 1);
    },
  },
};
</script>

<template>
  <div>
    <h1>To Do App</h1>

    <input type="text" placeholder="Type Here" v-model="newPerson" />
    <input type="text" placeholder="Type Here" v-model="newAge" />

    <button @click="addPerson()">Add Person</button>

    <ul>
      <li v-for="person in persons" :key="person.id">
        <div>{{ person.id }}</div>
        <div>{{ person.name }}</div>
        <div>{{ person.age }}</div>

        <button @click="removePerson(person.id)">Delete Person</button>
      </li>
    </ul>
  </div>
</template>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */

.container {
  margin: 5rem auto 0 auto;
}
</style>

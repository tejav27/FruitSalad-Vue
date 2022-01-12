<template>
  <div>
    <p>List-1</p>
    <ul>
      <button
        v-for="fruit in fruits"
        v-bind:key="fruit"
        v-on:click="addFruit(fruit)"
      >
        {{ fruit }}
      </button>
    </ul>
    <p>List-2</p>
    <ul>
      <li v-for="newFruit in newFruits" v-bind:key="newFruit">{{newFruit}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fruits: [
        "apple",
        "banana",
        "pear",
        "mango",
        "strawberry",
        "bluberry",
        "kiwi",
      ],
      newFruits: [],
      addThisFruit: "",
    };
  },
  methods: {
    addFruit(listFruit) {
        this.newFruits.push(listFruit)
    },
  },
};
</script>

<style>
</style>
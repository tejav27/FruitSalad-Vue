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
      <li v-for="newFruit in newFruits" v-bind:key="newFruit">{{newFruit.quantity}}st {{newFruit.fruitName}}</li>
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
      i:null
    };
  },
  methods: {
    addFruit(listFruit) {
        let matchedFruit=this.newFruits.find(fruit1=>fruit1.fruitName==listFruit)
            if(matchedFruit){
                matchedFruit.quantity++
            }
            else{
                this.newFruits.push({quantity:1,fruitName:listFruit})
            }
    },
  },
};
</script>

<style>
</style>
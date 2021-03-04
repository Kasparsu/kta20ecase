<template>
  <div>
    <div class="columns">
      <div class="column is-four-fifths">
        <input class="input" type="text" v-model="newItem">
      </div>
      <div class="column is-one-fifths">
        <button class="button" @click="addItem">Add item</button>
      </div>
    </div>
    <h3 class="is-size-3">{{ reversed }}</h3>
    <ItemList title="All Items" :items="items"></ItemList>
    <ItemList title="Done Items" :items="doneItems"></ItemList>
    <ItemList title="Not Done Items" :items="notDoneItems"></ItemList>
  </div>
</template>

<script>
import ItemList from "./ItemList";
export default {
  components: {ItemList},
  props: [],
  data(){
    return {
      newItem: '',
      items: [
        {name:'Sai', isDone: false, key: 0},
        {name:'Leib', isDone: true, key: 1},
        {name:'Õlu', isDone: false, key: 2},
        {name:'Piim', isDone: true, key: 3},
        {name:'Komm', isDone: false, key: 4},
      ]
    }
  },
  methods: {
    addItem() {
      if(this.newItem.trim() != ''){
        this.items.push({name:this.newItem, isDone: false, key: this.items.length});
      }
      this.newItem = '';
    }
  },
  computed: {

    // "hello" ['h', 'e', 'l', 'l', 'o'] 'olleh'
    reversed(){
      return this.newItem.split('').reverse().join('');
    },
    doneItems(){
      // return this.items.filter(function (item) {
      //     return item.isDone;
      // });

      // return this.items.filter(item => {
      //   return item.isDone;
      // });
      return this.items.filter(item => item.isDone);
    },
    notDoneItems(){
      return this.items.filter(item => !item.isDone);
    }
  }
}
</script>

<style>

</style>
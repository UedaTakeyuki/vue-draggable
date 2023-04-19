<template>
  <v-app>
    <v-main>
      <div>
        <draggable v-model="items" draggable=".item">
          <div v-for="item in items" :key="item.id" class="item">
            {{item.name}}
          </div>
        </draggable>
        <button @click="showItems">表示</button>
      </div>
    </v-main>
  </v-app>
</template>

<script>
import draggable from 'vuedraggable'
//const draggable = window['vuedraggable'];

export default {
  
  components: {
    draggable
  },
  data: () => ({
    items: [
      {
        id: 1,
        name: "ITEM - 1"
      },
      {
        id: 2,
        name: "ITEM - 2"
      },
      {
        id: 3,
        name: "ITEM - 3"
      },
      {
        id: 4,
        name: "ITEM - 4"
      },
    ],
  }),
  methods: {
    showItems() {
      alert(this.items.map(val => { return val.id }))
    }
  },
  mounted(){
    console.log("this", this)
    console.log("window", window)
  }
};
</script>

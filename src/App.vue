<template>
  <v-app>
    <v-main>
      <v-card
        class="mx-auto"
        max-width="500"
      > 
        <v-card-title> Draggable List </v-card-title>
        <v-card-text>
          <v-list>
            <draggable v-model="items" draggable=".item">
              <v-list-item v-for="item in items" :key="item.id" class="item"
                @click="showItems"
              >
                <v-list-item-content
                >
                  <v-list-item-title v-text="item.name"></v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </draggable>
            <button @click="showItems">表示</button>
          </v-list>
        </v-card-text>
      </v-card>
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

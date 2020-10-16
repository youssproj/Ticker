<template>
  <div class="info">
    <v-btn icon to="/">
      <v-icon>
        mdi-arrow-left
      </v-icon>
    </v-btn>
    <div>
      <v-col>
        <v-row>
          <h2>{{name}}</h2>
          <v-spacer></v-spacer>
          <button @click="overlay = true" icon>
            <v-icon>
              mdi-dots-horizontal
            </v-icon>
          </button>
        </v-row>
        <v-row>
          <p>{{description}}</p>
        </v-row>
        </v-col>
        <v-overlay :value="overlay" absolute>
            <EditTask 
            @close="close" 
            :name="name"
            :description="description"/>
        </v-overlay>
    </div>
  </div>
</template>

<script>
import EditTask from '@/components/EditTask.vue'
export default {
    name: "Info",
    components: {
      EditTask
    },
    props: ["name","description"],
    data(){
        return{
          edit: false,
          overlay: false,
        }
    },
    methods: {
      addChecklist(){
        console.log("Checklist")
      },
      close(){
        this.overlay = false
        console.log("this is the close function")
      }
    }
}
</script>

<style>

#edit{
  z-index: 10;
  position: absolute;
  height: 100%;
  width: 100%;
}

</style>
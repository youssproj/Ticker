<template>
  <div class="edit-task">
      
          <v-card>
              <h2>Edit</h2>
            <v-text-field v-model="name"></v-text-field>
            <v-text-field v-model="description"></v-text-field>
            <v-btn @click="close">Close</v-btn>
          </v-card>

  </div>
</template>

<script>
export default {
    name: 'EditTask',
    props: ["name", "description"],
    data(){
        return{
            overlay: false

        }
    },
    methods:{
        close(){
            let newData = {name: this.name, description: this.description}
            this.$emit('close', newData)
        }
    }
}
</script>

<style>

</style>
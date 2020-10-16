<template>
  <div class="new-task">
      <v-btn to="/"></v-btn>
      <v-col >
          <v-row>
            <v-text-field placeholder="Name"></v-text-field>
          </v-row>
          <v-row>
              <v-text-field placeholder="Description"></v-text-field>
            </v-row>
      </v-col>
  </div>
</template>

<script>
export default {
    name: "NewTask",
    data(){
        return{

        }
    },
    methods: {

    }
}
</script>

<style>

</style>
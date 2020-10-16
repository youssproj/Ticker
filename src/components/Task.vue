<template>
  <div class="task">
      <div class="align-center text-center d-flex justify-space-around">
        <div class="checkbox">
            <!-- <div @click='test' class="circle" :class="{green: tick, red: !tick}"></div> -->
            <v-checkbox 
                :disabled="disabled"
                class="checkbox mx-6"
                color="success"
                @click="disabled = true"
                >
            </v-checkbox>
        </div>
        <div class="mx-6">
            <h3 id="name">{{name}}</h3>
        </div>
        <div class="arrow-button">
            <v-btn @click="toInfo" icon class="mx-6">
                <v-icon>
                    mdi-dots-horizontal
                </v-icon>
            </v-btn>
        </div>
      </div>
  </div>
</template>

<script>
export default {
    name: "Task",
    props: ["name", "completed", "description"],
    data() {
        return{
            disabled: false
        }
    },
    methods: {
        test(){
            console.log("test")
            this.tick = true
            this.completed = true
            this.$emit('taskCompleted', this.completed)  
        },
        toInfo(){
            this.$router.push({name: "Info", params: {name: this.name, description: this.description}})
        }
    }
}
</script>

<style scoped>
#name{
    min-width: 40vw;
}

</style>
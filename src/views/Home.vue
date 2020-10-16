<template>
  <v-app>
      <div class="header justify-space-between">
        <h1 class="ma-4">Daily Checklist</h1>
        <v-btn to="/new-task" class="ma-4" icon>
          <v-icon>mdi-plus</v-icon>
        </v-btn>
      </div>
      <hr>
      <div class="routine">
        <div class="tasks-container">
            <Task 
                id="task" 
                v-for="r in routine" :key="r.id"
                :name="routine[r.id].name"
                :completed="routine[r.id].completed"
                :description="routine[r.id].description"
                @taskCompleted="r.completed = true"
                />
        </div>
        <div class="task-description">
        </div>
      </div>
  </v-app>
</template>

<script>
import Task from "../components/Task.vue"
export default {
    name: "App",
    components: {
        Task,
        // Info
    },
    data(){
        return{
            routine: [
                {name: "Make the Bed", completed: false, id: 0,
                showMore: true,
                description: "Making the Bed is the best start to the day, and easy first task!",
                image: ""},
                {name: "Brush Teeth", completed: false, id: 1,
                showMore: false,
                description: "Brushing Everyday is goo for you",
                image: ""},
                {name: "Exercise", completed: false, id: 2,
                showMore: false,
                description: "Get up you fat cunt",
                image: ""},
                {name: "Practice the Drums", completed: false, id: 3,
                showMore: false,
                description: "Mad cunts are drummers",
                image: ""},
                {name: "Read", completed: false, id: 4,
                showMore: false,
                description: "At least a page of something everyday please sir",
                image: ""},
                {name: "Listen to new Music", completed: false, id: 5,
                showMore: false,
                description: "Listen to a new song and think desciption it. listen a few times to really get a feel for it.",
                image: ""}
            ],
            showing: {}
        }
    },
    created(){
        for(let i=0; i<this.routine.length; i++){
            if(this.routine[i].showMore == true ){
                this.showing = this.routine[i]
            }
        }
    },
    methods: {
        test(){
            console.log("test")
        },
        changeView(e){
            console.log(e)
            this.showing = {}
            for(let i=0; i<this.routine.length; i++){
                if(this.routine[i].name == e){
                    this.showing = this.routine[i]
                }else{
                    this.routine[i].showMore = false
                }
            }
        }
    }
}
</script>

<style scoped>
.header{
    display: flex;
    justify-content: space-between;
}
#info{
    margin: 30px;
}
.routine{
    display: flex;
}
.tasks-container{
    min-height: 83vh;
    max-height: 84vh;
    display: flex;
    margin: 10px 0px;
    justify-content: space-evenly;
    flex-direction: column;
}
#slot{
    width: 25vw;
    height: 20px;
    flex: 1;
    padding: 4px;
}
.slot:hover{
    background-color: grey;
    padding: auto;
}
</style>
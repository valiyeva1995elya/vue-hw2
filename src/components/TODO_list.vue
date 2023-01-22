<script>


export default {
    data() {
        return {
            tasks: [
                {
                    name: 'clean', 
                }
            ],
            name: " ",
            counter: 0,
        }
    },
    methods: {
        addTask() {
            const newTask = {
                name: this.name,
            }
            this.tasks.push(newTask)
            this.name = "";
            
        },
        deleteTask(this.name){
            tasks.filter(item => item == name)
            console.log("ok")
        }
       
    }
}
</script>

<template>
    <div class="block-compl">
        <p> {{ counter }} task(s) left!</p>
        <div class="add_task">
            <form @submit.prevent>
                <input v-bind:value="name" 
                    @input="name = $event.target.value" 
                    type="text" 
                    class="input"
                    placeholder="Add a new task">
                <button @click="addTask" class="btn">
                    Add
                </button>
            </form>
        </div>
        <div class="task" v-for="task in tasks">
            <input type="checkbox">
            <div>{{ task.name }}</div>
            <button class="btn2" @click="deleteTask">X</button>
        </div>
    </div>
</template>

<style scoped>
    .task{
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 97%;
        height: 20px;
        border: 1px solid rgb(180, 179, 179);
        padding: 5px 15px;
        
    }
    .block-compl{
        margin: 25px;
    }
    .input{
        width: 95%;
        background-color: black;
        border: 1px solid rgb(180, 179, 179);
        margin: 0 10px 20px 0;
        border-radius: 3px;
        color: white;
    }
</style>
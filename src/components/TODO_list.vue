<script>

export default {
    data() {
        return {
            tasks: [],
            counter: 0,
            newText: "",
            counter: 0,
            doneTasks: [],
            isEdit: false,
            edit: [],
        }
    },
    methods: {
        addTask() {
            if (this.newText == "") {
                return
            }
            let newTask = {
                id: this.tasks.length + 1,
                text: this.newText,
                isDone: false
            }

            this.tasks.push(newTask)
            this.newText = "";
            console.log(this.tasks);
            

        },

        deleteTask(id) {
            this.tasks = this.tasks.filter(task => task.id != id)
        },
        
        hide() {
            this.tasks = this.tasks.filter(task => task.isEdit != true)
             
            
        }

    }
}
</script>

<template>
    <div class="block-compl">
        <div class="block">
            <p> {{ counter }} task(s) left!</p>
            <button @click="hide()" >Hide Completed</button> 
        </div>
        <div class="add_task">
            <form @submit.prevent>
                <input v-bind:value="newText" @input="newText = $event.target.value" type="text" class="input" placeholder="Add a new task">
                <button @click="addTask" class="btn">
                    Add
                </button>
            </form>
        </div>
        <div class="task" v-for="task in tasks" :class="{done: task.isEdit}">
            <input type="checkbox" @change="task.isEdit = !task.isEdit">
            <div>{{ task.text }}</div>
            <button class="btn2" @click="deleteTask(task.id)">X</button>

        </div>
    </div>
</template>

<style scoped>
.task {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 97%;
    height: 20px;
    border: 1px solid rgb(180, 179, 179);
    padding: 5px 15px;

}

.block-compl {
    margin: 25px;
}
.block{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
button{
    background-color: black;
    color: white;
    border-radius: 5px;
}
.input {
    width: 95%;
    background-color: black;
    border: 1px solid rgb(180, 179, 179);
    margin: 0 10px 20px 0;
    border-radius: 3px;
    color: white;
}

.done {
    text-decoration: line-through;
}
.list{
    display: none;
}
</style>
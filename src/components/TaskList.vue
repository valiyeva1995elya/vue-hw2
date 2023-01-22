<script>

</script>

<template>
    <div class="task" v-for="task in tasks">

        <div>{{ task.name }}</div>
        <button class="btn2" @click="deleteTask">X</button>
    </div>
</template>

<style scoped>
.task{
    background-color: aqua;
}
</style>
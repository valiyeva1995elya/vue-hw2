<script>

</script>

<template>
    <div class="add_task">
            <form >
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
    
</template>

<style scoped> 
</style>
<template>
    <form @submit.prevent="handleSumit">
        <input
        type="text"
        placeholder="write the task...."
        v-model="newTask"
        >
        <button>Add</button>
    </form>
</template>

<script>
import { useTaskStore } from '@/stores/TaskStore';
import { ref } from 'vue';

    export default {
        setup() {
            const TaskStore = useTaskStore()
            const newTask = ref('')
            const handleSumit = () => {
                if(newTask.value.length > 0) {
                    TaskStore.addTask({
                        title: newTask.value,
                        isFav: true,
                        id: Math.floor(Math.random() * 100)
                    })
                    newTask.value = ''
                }   

            }
            return {handleSumit , newTask}
        }
        
    }
</script>
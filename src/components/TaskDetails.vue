<template>
    <div>
        <div class="task">
            <h3>{{ task.title }}</h3>
            <div class="icons">
                <i
                @click="TaskStore.deleteTask(task.id)"
                class="material-icons">delete</i>
                <i 
                @click="TaskStore.toggleFav(task.id)"
                class="material-icons">favorite</i>
            </div>
            

        </div>

    </div>
</template>

<script>
import { useTaskStore } from '@/stores/TaskStore';

    export default {
        props:['task'],
        setup() {
            const TaskStore = useTaskStore()
            return {TaskStore }
        }
        
        
    }
</script>
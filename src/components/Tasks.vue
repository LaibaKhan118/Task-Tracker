<script setup>
import Task from './Task.vue'

</script>
<template>
    <div :key="task.id" v-for="task in tasks">
        <Task @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)"
            :task="task" />
    </div>
</template>



<script>
export default {
    name: 'Tasks',
    props: {
        tasks: Array
    },
    Components: {
        Task
    },
    emits: ['delete-task', 'toggle-reminder']
}
</script>
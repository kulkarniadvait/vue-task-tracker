<template>
    <div v-for="item in tasks" :key="item.id" >
        <Task @toggle-reminder="$emit('toggle-reminder',item.id)" @delete-task="$emit('delete-task',item.id)" :task='item' />
    </div>
    
</template>

<script>
import Task from './Task.vue'
    
export default {
    name: 'Tasks',
    props: {
        tasks: Array
    },
    components: {
        Task
    },
    emits: ['delete-task','toggle-reminder']

}
</script>
<template>
    <div class="tasks_container">
        <div class="tasks_content">
            <h1>Tasks</h1>
            <ul class="tasks_list">
                <li v-for="task in tasks" :key="task.id">
                    <h2>{{ task.title }}</h2>
                    <p>{{ task.description }}</p>
                    <button @click="toggleTask(task)">
                        {{ task.completed ? 'Undo' : 'Complete' }}
                    </button>
                    <button @click="deleteTask(task)">Delete</button>
                </li>
            </ul>
        </div>
    </div>
</template>
<script>
    export default{
        data(){
            return{
                tasks:[]
            }
        },
        methods:{
            async getData(){
                try{
                    const response = await this.$http.get('http://127.0.0.1:8000/api/tasks/');
                    this.tasks = response.data;
                }catch(error){
                    console.log(error)
                }
            },
        },
        created(){
            this.getData();
        }
    }
</script>
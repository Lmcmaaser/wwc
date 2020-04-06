<template>
    <div>
        <header>
            <h1>To Do</h1>
        </header>
        <form>
            <input placeholder='add a task' v-model="newTask" @keyup.enter="addTask($event)"/> 
            <!-- v-model watches newTask and binds what you are typing to the addTask function-->
        </form>
        <section>
            <ul>
                <!-- v-for = a for loop -->
                <!-- :class is checking for true/false, if truth, then do the thing -->
                <li 
                    v-for='task in tasks'  
                    v-bind:key='task.id'
                    :class="{'done': task.done}"
                >
                    <input type="checkbox" v-model="task.done" @click="complete"/>
                    {{task.text}}
                </li>
            </ul>
        </section>
    </div>
</template>

<script>
export default {
    // static data
    data() {
        return {
            newTask: "",
            tasks: [
                {
                    text: 'Learn Vue',
                    done: false
                },
                {
                    text: 'Finish Thinkful',
                    done: false
                }   
            ]
        }
    },
    methods: { 
        //put your functions
        addTask(event) {
            event.preventDefault()
            this.tasks.push({text: this.newTask, done: false})
            this.newTask = '' //sets newTask back to an empty string
        },
        complete(task) {
            task.done = true
        }
    } 
}
</script>

<style scoped> 
    /* scoped is like global */
    .done {
        text-decoration-line:line-through
    }
</style>
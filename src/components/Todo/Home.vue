<template>
    <div class="container">
        <div class="form-data">
            <form>
                <div class="mb-3">
                    <label for="exampleInputEmail1" class="form-label">Name</label>
                    <input type="text" v-model="todoData.name" class="form-control" id="exampleInputEmail1"
                        aria-describedby="emailHelp">
                </div>
                <div class="mb-3">
                    <label for="exampleInputEmail1" class="form-label">Task</label>
                    <textarea class="form-control" v-model="todoData.task" id="" rows="10" cols="30"></textarea>
                </div>
                <div class="mb-3">
                    <label for="exampleInputEmail1" class="form-label">Task</label>
                    <input type="date" class="form-control" v-model="todoData.date" id="exampleInputEmail1"
                        aria-describedby="emailHelp">
                </div>
            
            </form>
            <button @click="addDaata()" class="btn btn-primary">Submit</button>
        </div>
        <div>
            <div class="table-responsive">
                <table class="table align-middle">
                    <thead>
                        <tr>
                            <th>name </th>
                            <th>task</th>
                            <th>date</th>
                        </tr>
                    </thead>
                    <tbody>

                        <tr v-for="i in tbData" :key=i>
                            <td>{{ i.name }} </td>
                            <td>{{ i.task }}</td>
                            <td>{{ i.date }}</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>
<script setup>
import { ref } from 'vue';

let todoData = ref({
    "name": "",
    "task": "",
    "date": ""
})

let tbData = ref([{ name: 'sameer', task: "learn", "date": 'ssss' }])

const addDaata = () => {
    tbData.value.push(todoData.value)
    todoData.value = {}
}
</script>

<!--  Css import  -->
<style lang="css">
@import url('./Home.css');
</style>
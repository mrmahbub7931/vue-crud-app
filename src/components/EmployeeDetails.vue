<template>
    <p class="text-black m-5">Employee Details page</p>
    <p v-if="employees.length < 1">No records Found!</p>
    <div class="overflow-x-auto" v-else>
    <table class="table w-full">
        <!-- head -->
        <thead>
        <tr>
            <th>Id</th>
            <th>Name</th>
            <th>Email</th>
            <th>Action</th>
        </tr>
        </thead>
        <tbody>
        <!-- row 1 -->
        <tr v-for="employee in employees" v-bind:key="employee.id">
            <th>{{employee.id}}</th>
            <td>{{employee.name}}</td>
            <td>{{employee.email}}</td>
            <td>
                <button class="btn btn-warning ">Edit</button>
                <button class="btn btn-error ml-4">Delete</button>
            </td>
        </tr>
        </tbody>
    </table>
</div>
</template>
<script>
    export default {
        name: 'employee-details',
        props: {
            employees: Array
        }
    }
</script>
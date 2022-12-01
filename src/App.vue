<template>
      <h1 class="text-center text-2xl">CRUD APPLICATION</h1>
      <div class="m-8 bg-sky-100 h-screen">
          <employee-details v-bind:employees ="employees" @edit="editEmployee"></employee-details>
      </div>
</template>

<script>
  import EmployeeDetails from './components/EmployeeDetails.vue';

  export default {
    name: 'app',
    components: {
      EmployeeDetails
    },
    data(){
        return {
            employees: []
        }
    },
    methods: {
        async getEmployees(){
            try {
                const response = await fetch(`https://jsonplaceholder.typicode.com/users`)
                const data = await response.json()
                this.employees = data
            } catch (error) {
                console.error('Error occured while retrieving employees: ' +error);
            }
        },

        async editEmployee() {
            
        }
    },
    mounted() {
        this.getEmployees()
    }
  }
</script>

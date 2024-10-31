<template>
  <div>
    <input v-model="filter" placeholder="Фільтр за спеціальністю..." />
    <div v-for="employee in filteredEmployees" :key="employee.id">
      <EmployeeItem :employee="employee" @delete="deleteEmployee" />
    </div>
  </div>
</template>

<script>
import EmployeeItem from './EmployeeItem.vue';

export default 
{
  components: { EmployeeItem },
  data() 
  {
    return {
      employees: [],
      filter: ''
    };
  },
  computed: {
    filteredEmployees() 
    {
      return this.employees.filter(employee =>
        employee.specialty.toLowerCase().includes(this.filter.toLowerCase())
      );
    }
  },
  methods: 
  {
    deleteEmployee(id) 
    {
      this.employees = this.employees.filter(employee => employee.id !== id);
    }
  },
  mounted() 
  {
    fetch('/employees.json')
      .then(response => response.json())
      .then(data => 
      {
        this.employees = data;
      });
  }
};
</script>

<style scoped>
.employee-list 
{
  display: flex;
  flex-direction: column;
  gap: 15px;
}

input 
{
  padding: 8px;
  font-size: 16px;
  margin-bottom: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
  width: 100%;
}
</style>
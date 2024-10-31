<template>
    <div>
      <h1>Список співробітників</h1>
      <EmployeeList />
    </div>
  </template>
  
  <script>
  import EmployeeList from '@/components/EmployeeList.vue';
  
  export default 
  {
    components: { EmployeeList }
  };
</script>  
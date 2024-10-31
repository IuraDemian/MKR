<template>
  <div class="employee-item">
    <h3>{{ employee.name }}</h3>
    <p>Паспорт: {{ employee.passport }}</p>
    <p>Освіта: {{ employee.education }}</p>
    <p>Спеціальність: {{ employee.specialty }}</p>
    <p>Посада: {{ employee.position }}</p>
    <p>Оклад: {{ employee.salary }} грн</p>
    <button @click="$emit('delete', employee.id)">Видалити</button>
  </div>
</template>

<script>
export default 
{
  props: 
  {
    employee: Object
  }
};
</script>

<style scoped>
.employee-item 
{
  border: 1px solid #ddd;
  padding: 15px;
  border-radius: 8px;
  background-color: #fff;
}

h3 
{
  margin: 0 0 5px;
  color: #007bff;
}

p 
{
  margin: 4px 0;
  color: #555;
}

button 
{
  background-color: #ff4d4d;
  color: #fff;
  padding: 8px 12px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 14px;
}

button:hover 
{
  background-color: #ff1a1a;
}
</style>
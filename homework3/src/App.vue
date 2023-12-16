<template>
  <div>
    <h2>Список сотрудников</h2>
    <ul>
      <li v-for="employee in employees" :key="employee.id">
        {{ employee.id }} - {{ employee.name }} - {{ employee.salary }} - {{ employee.position }}
        <button @click="deleteEmployee(employee.id)">Удалить</button>
      </li>
    </ul>

    <button @click="addNewEmployee">Добавить сотрудника</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      employees: [
        { id: 1, name: 'John Doe', salary: '1000$', position: 'Менеджер' },
        { id: 2, name: 'Jane Smith', salary: '2000$', position: 'Разработчик' },
        { id: 3, name: 'Mike Johnson', salary: '1500$', position: 'Дизайнер' },
      ],
    };
  },
  methods: {
    deleteEmployee(id) {
      this.employees = this.employees.filter(employee => employee.id !== id);
    },
    addNewEmployee() {
      let newEmployee = {
        id: this.employees.length + 1,
        name: 'John',
        salary: '0$',
        position: 'Сотрудник',
      };
      this.employees.push(newEmployee);
    },
  },
};
</script>
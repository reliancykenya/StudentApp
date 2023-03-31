<template>
  <div>
    <h2>Student List</h2>
    <ul>
      <li v-for="(student, index) in students" :key="index" @click="showDetails(student)">
        {{ student.name }}
      </li>
    </ul>
    <StudentDetails ref="details"></StudentDetails>
  </div>
</template>

<script>
import StudentDetails from './StudentDetails.vue';

export default {
  components: {
    StudentDetails,
  },
  data() {
    return {
      students: [
        { id: 1, name: 'John', age: 18 },
        { id: 2, name: 'Mary', age: 19 },
        { id: 3, name: 'Peter', age: 20 },
      ],
    };
  },
  methods: {
    showDetails(student) {
      this.$refs.details.showDetails(student);
    },
  },
};
</script>

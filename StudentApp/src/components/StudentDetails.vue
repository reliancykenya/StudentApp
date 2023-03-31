<template>
    <div>
      <h2>Student Details</h2>
      <p>Name: {{ student.name }}</p>
      <p>Age: {{ student.age }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        student: {},
      };
    },
    methods: {
      showDetails(student) {
        this.student = student;
      },
    },
  };
  </script>
  
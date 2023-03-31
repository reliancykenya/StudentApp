<template>
  <student-card v-for="student in students" :key="student.id"
  :id="student.id"
  :name="student.name"
  :age="student.age"
  :course="student.course"
  @delete-student="deleteStudent"

  
  >
  </student-card>


  <add-student-form @add-student="addStudent"
  
  ></add-student-form>
</template>


<script>
import AddStudentForm from './components/AddStudentForm.vue';
import StudentCard from './components/StudentCard.vue';
import StudentListVue from './components/StudentList.vue';
export default {
  created(){
    console.log(' create called')
  },
  beforeMount(){
    console.log('before mount called')
  },
  mounted(){
    console.log('mounted called')
  },
  beforeCreate(){
    console.log('before create called')
  },
 
  beforeUpdate(){
    console.log('view about to be updated')
  },
  updated(){
    console.log('view updated')
  },
  components: { StudentCard, AddStudentForm, StudentListVue },
  data() {
    return {
      students: [
        { id: 1, name: "mercy", age: 12, course: "software" },
        { id: 2, name: "joy", age: 32, course: "cyber" },
        { id: 3, name: "paul", age: 43, course: "database" },
      ],
    };
  },
  methods:{
    deleteStudent(id){
      this.students=this.students.filter(student=>student.id!==id);

    },
    addStudent(name,age,course){
      const newStude={
        id:new Date().toISOString,
        name:name,
        age:age,
        course:course,
      };
      this.students.push(newStude);


    }
  }
};
</script>

<style></style>

<template>
 <form @submit.prevent>
    <div class="mb-3">
    <label for="student_name" class="form-label"
      >Name</label
    >
    <input
      type="text"
      class="form-control"
      id="student_name"
      name="student_name"
      v-model="student_name"
      ref="studentName"

    />
  </div>
  <div class="mb-3">
    <label for="student_age" class="form-label"
      >Age</label
    >
    <input
      type="Number"
      class="form-control"
      id="student_age"
      name="student_age"
      v-model="student_age"
      ref="studentAge"
    />
  </div>
  <div class="mb-3">
    <label for="student_course" class="form-label"
      >Course</label
    >
    <input
      type="text"
      class="form-control"
      id="student_course"
      name="student_course"
      v-model="student_course"
      ref="studentCourse"
    />
  </div>
  <div class="mb-3">
    <button class="btn btn-success" @click="addStudent">Add Student</button>
  </div>
 </form>
  
</template>

<script>
export default {
data(){
    return {
        student_name:'',
        student_age:null,
        student_course:'',

    };
},
methods:{
    addStudent(){
        this.$emit('add-student',this.student_name,this.student_age,this.student_course);
        this.student_name='';
        this.student_age=null;
        this.student_course='';
        console.log(this.$refs.studentName.value);
        console.log(this.$refs.studentAge.value);
        console.log(this.$refs.studentCourse.value);

    }
}

};
</script>

<style></style>

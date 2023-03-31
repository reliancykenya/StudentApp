<template>
  <div class="card">
    <div class="card-header">Name:{{ name }}</div>
    <div class="card-body">
      <h5 class="card-title">Course:{{ course }}</h5>
      <h5 class="card-title">Course:{{ id }}</h5>
      <!-- <p id="para">

      </p> -->
      <p class="card-text">
        age:{{ age }}
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorem
        possimus alias fugit enim voluptatem mollitia iusto, ipsum amet sed
        nostrum dignissimos atque unde quisquam tempora neque cum doloribus in
        delectus!
      </p>
      <a href="#" class="btn btn-danger" @click="deleteStudent">Delete</a>
      <a href="#" class="btn btn-primary">Update</a>
    </div>
  </div>

  <!-- <Teleport to="#para">
    <h1>hello Teleport</h1>
  </Teleport> -->
</template>

<script>
export default {
  props: ["id", "name", "course", "age"],
  methods:{
    deleteStudent(){
        this.$emit('delete-student',this.id);

    },

  },
};
</script>

<style></style>

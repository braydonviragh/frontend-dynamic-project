<template>
  <div id="app">
    <div v-for="student in studentData.students">
      <Student :key="student.id" 
      v-bind:firstName='student.firstName' 
      v-bind:email='student.email'
      v-bind:city='student.city'
      v-bind:company='student.company'
      v-bind:lastName='student.lastName'
      v-bind:pic='student.pic'
      v-bind:skill='student.skill'
      
      />
    </div>
  </div>
</template>
<script>
import Student from './components/Student.vue';
export default {
  name: "App",
  components:{
    Student
  },
  data() {
    return {
      studentData: {},
    }
  },
  created(){
    this.getStudents();
  },
  methods: {
    async getStudents(){
      const res = await fetch('https://api.hatchways.io/assessment/students');
      const data = await res.json();
      this.studentData = data;
      this.studentData = JSON.parse(JSON.stringify(this.studentData));
      console.log(JSON.parse(JSON.stringify(this.studentData.students)));
    }
  }
};
</script>


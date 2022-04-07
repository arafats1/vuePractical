<template>
  <div>   
  <div>
    <StudentRegistrationForm />
  </div>
  <div>
    <RegisteredStudentsTable />
  </div>
 </div>
 

</template>

<script>
import StudentRegistrationForm from "./components/StudentRegistrationForm.vue";
import RegisteredStudentsTable from "./components/RegisteredStudentsTable.vue";
export default {
  name: "App",
  data(){
    return {
      students: [{
        firstname:'Nina',
        lastname: 'Kenyo',
        email:'nina@gmail.com',
        phonenumber:'0782222222'
      },
      {
        firstname:'Kylie',
        lastname: 'Namu',
        email:'namu@gmail.com',
        phonenumber:'0782452723'
      }]
    }
  },
  computed() {},
  components: {
    StudentRegistrationForm,
    RegisteredStudentsTable
  },
};
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
*{
    margin: 0;
    padding:0;
    box-sizing:border-box;
}

.heading{
    margin-left: 120px;
    margin-top: 30px;
    color: red;
}
#student-form{
    margin: auto; 
    /* width:50%; */
    /* margin: 20px 600px 100px 100px; */
}
#student-table{
    width: 90%;
    margin-left: 30px;
}
.forms{
    margin: auto; 
    /* width:80%; */
    margin-bottom: 100px;
    /* background-color: red; */
    /* margin-right: 10px; */
}

</style>

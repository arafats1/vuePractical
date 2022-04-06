<template>
  <div>
    <student-registration-form /> 
  </div>
</template>

<script>
import StudentRegistrationForm from "./components/StudentRegistrationForm.vue";
export default {
  name: "App",
  computed() {},
  components: {
    StudentRegistrationForm
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

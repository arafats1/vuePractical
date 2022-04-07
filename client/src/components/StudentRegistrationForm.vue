<template>
  <div>
    <div class="row">
      <div class="col-3"></div>
      <div class="col-6">
        <div class="forms">
          <form id="student-form">
            <h3 class="heading">STUDENTS REGISTRATION</h3>
            <div v-if="isRegistered" class="alert alert-success" role="alert">
              Student has been registered successfully
            </div>
            <div class="mb-3">
              <label for="exampleInputfirstName" class="form-label"
                >FIRST NAME</label
              >
              <input
                v-model="student.firstname"
                type="text"
                class="form-control"
                id="exampleInputfirstName"
                name="firstname"
              />
            </div>
            <div class="mb-3">
              <label for="exampleInputlastName" class="form-label"
                >LAST NAME</label
              >
              <input
                v-model="student.lastname"
                type="text"
                class="form-control"
                id="exampleInputlastName"
                name="lastname"
              />
            </div>
            <div class="mb-3">
              <label for="exampleInputphoneNumber" class="form-label"
                >PHONE NUMBER</label
              >
              <input
                v-model="student.phonenumber"
                type="text"
                class="form-control"
                id="exampleInputphoneNumber"
                name="phonenumber"
              />
            </div>
            <div class="mb-3">
              <label for="exampleInputEmail" class="form-label">EMAIL</label>
              <input
                v-model="student.email"
                type="email"
                class="form-control"
                id="exampleInputEmail"
                name="email"
              />
              <div id="emailHelp" class="form-text">
                We'll never share your email with anyone else.
              </div>
            </div>
            <button @click="registerStudent" class="btn btn-primary">
              Submit
            </button>
          </form>
        </div>
      </div>
      <div class="col-3"></div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "StudentRegistrationForm",
  data() {
    return {
        isRegistered:false,
      student: {
        firstname: "",
        lastname: "",
        phonenumber: "",
        email: "",
      },
    };
  },
  methods: {
    async registerStudent() {
      await axios
        .post("http://localhost:3000/api/student", this.student)
        .then((response) => {
            console.log(response);
          if (response.message == 'Student registered!'){
              this.isRegistered = true
          }
        });
    },
  },
  // mounted(){

  // },
  components: {},
};
</script>
<style>
</style>
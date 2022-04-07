<template>
   <div class="row">
       <div class="col">
           <div>
            <h3 class="heading">REGISTERED STUDENTS</h3>
            <table class="table" id="student-table">
                <thead>
                  <tr>
                    <th scope="col">First Name</th>
                    <th scope="col">Last Name</th>
                    <th scope="col">Phone Number</th>
                    <th scope="col">Email</th>
                    <th scope="col">Action</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for = "student,index in students" :key="student.lastname">
                    <td>{{student.firstname}}</td>
                    <td>{{student.lastname}}</td>
                    <td>{{student.phonenumber}}</td>
                    <td>{{student.email}}</td>
                    <td>
                      <button type="submit" class="btn btn-primary">Edit</button>

                      <button type="submit" class="btn btn-danger">Delete</button>
                    </td>
                   
                  </tr>
                </tbody>
              </table>
        </div>
       </div>
       
    </div> 
</template>

<script>
import axios from 'axios'
export default {

    name:"RegisteredStudentsTable",
    data(){
    return {
      students: []
    }
    },
    async mounted(){
        
        await axios.get('http://localhost:3000/api/studentData')
        .then((response)=> {
            // console.log(response.data.data)
            this.students = response.data.data
        })
        console.log('Component has been mounted');
    }
  
}
</script>

<style>

</style>
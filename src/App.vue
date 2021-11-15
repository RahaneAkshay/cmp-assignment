<template>
  <div class="container-fluid">
    <div class="row mt-5">
      <div class="col-6">
          <table class="table">
  <thead>
    <tr>
         <th scope="col">Sr.No</th>
      <th scope="col">Name</th>
      <th scope="col">Age</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(user,index) in users" :key="index">
      <th scope="row">{{index +1}}</th>
      <td>{{user.name}}</td>
      <td>{{user.age}}</td>
    </tr>
  </tbody>
</table>

      </div>
      <div class="col-6">
          <user-data @send-userData="getUserData($event)"></user-data>
      </div>
    </div>
  </div>
</template>
<script>
export default {
    data(){
        return{
            users:[]
        }
    },
    methods:{
        getUserData(value){
           this.users.push(value)
        }
    }
};
</script>

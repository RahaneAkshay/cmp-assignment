<template>
    <input type="text" class="form-control" v-model="name"><br>
    <input type="number" class="form-control" v-model="age"><br>
    <button type="button" class="btn btn-primary" @click="submitForm()">Submit</button>
</template>
<script>
export default {
    emits:['send-userData'],
    data(){
        return{
            name:'',
            age:''
        }
    },
    methods:{
        submitForm(){
            const user = {
                name:this.name,
                age:this.age
            }
            
            this.$emit('send-userData',user)
        }
    }
}
</script>
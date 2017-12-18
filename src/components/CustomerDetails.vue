<template>
  <div class="customerdetails container">
      <h1 class="page-header">
        {{customer.name}}
      </h1>
      <ul class="list-group">
        <li class="list-group-item"><span class="glyphoicon glyphicon glyphicon-asterisk"> {{customer.phone}}</span></li>
        <li class="list-group-item"><span class="glyphoicon glyphicon glyphicon-asterisk"> {{customer.email}}</span></li>
      </ul>

      <ul class="list-group">
        <li class="list-group-item"><span class="glyphoicon glyphicon glyphicon-asterisk"> {{customer.education}}</span></li>
        <li class="list-group-item"><span class="glyphoicon glyphicon glyphicon-asterisk"> {{customer.graduationschool}}</span></li>

        <li class="list-group-item"><span class="glyphoicon glyphicon glyphicon-asterisk"> {{customer.profession}}</span></li>
        <li class="list-group-item"><span class="glyphoicon glyphicon glyphicon-asterisk"> {{customer.profile}}</span></li>

      </ul>
  </div>
</template>

<script>
export default {
  name: 'customerdetails',
  data () {
    return {
        customer:""
    }
  },
  methods:{
    fetchCustomers(id){
      this.$http.get("http://localhost:3000/users/"+id).then(function(response){
          this.customer = response.body
      })
    }
  },
  created(){
    this.fetchCustomers(this.$route.params.id)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

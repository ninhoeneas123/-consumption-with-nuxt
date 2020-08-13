<template>
  <div class="container">

  <v-list  outlined="true" class="users">

    <v-list-title>
     <h2>Usuarios</h2>
    </v-list-title> 

      <v-list-item link="true" tile="true" v-for="user in users":key="user.id">

       <v-list-item-content>
         <v-list-item-title> {{user.id}}    {{user.name}} </v-list-item-title>
         <v-list-item-subtitle> {{user.email}} </v-list-item-subtitle>
         <v-list-item-subtitle>{{user.address.street}},{{user.address.city}}</v-list-item-subtitle>
         <v-list-item-subtitle><v-divider role="presentation" aria-orientation="horizontal"></v-divider></v-list-item-subtitle>
        </v-list-item-content>

         
      </v-list-item>
     

    </v-list>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData () {
    const { data } = await axios.get('https://jsonplaceholder.typicode.com/users')
    return { users: data }
  }
}

</script>

<style scoped>
.container {
  text-align: center;
  margin-top: 100px;
  font-family: sans-serif;
}
.users {
 color: white;
}
.elements{
  border-bottom: 1px solid #e0e0e0 ;
 


}
</style>

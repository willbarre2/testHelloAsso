<template>
  <div class="card-container" v-for="user in users" :key="user.id">
    <img :src="user.avatar" alt="avatar utilisateurs">
    <div class="names-email-container">
        <p>{{ user.first_name + " " + user.last_name }}</p>
        <p>{{ user.email }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Cards',
  data(){
    return{
      users: [{first_name: "jojo"}]
    };
  },
  created(){
        const axios = require('axios').default;
        axios
        .get("https://reqres.in/api/users")
        .then((response) => {
            this.users = response.data.data
        })
        .catch((error) => console.log(error));
    },
}
</script>

<style scoped lang="scss">

$border: 2px solid black;
.card-container{
    width: 350px;
    display: flex;
    padding: 1rem;
    margin: 1rem;
    border: $border;
    border-radius: 25px;

    img{
        width: 128px;
        border: $border;
        border-radius: 50%;
    }
    .names-email-container{
        padding: 1rem;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        
        p{
            margin-top: .5rem;
        }
        
        p:first-child{
            margin-top: 0;
            font-weight: bold;
        }

    }
}
</style>
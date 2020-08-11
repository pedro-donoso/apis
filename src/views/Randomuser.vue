<template>
<div id="random">
  <div class="card-body" v-for="item in lists" :key="item">
  <img :src="item.picture.large" class="card-image"/>
    <h5 class="card-title">{{ item.name.title }} {{ item.name.first }} {{ item.name.last }}</h5>
    <p class="card-text">{{ item.gender }}</p>
            <p class="card-text">{{ item.location.street.name }} #{{
          item.location.street.number
        }}</p>
                <p class="card-text">{{ item.location.city }}</p>
                    <p class="card-text">{{ item.location.state }}</p>
                        <p class="card-text">{{ item.location.country }}</p>
                            <p class="card-text">{{ item.email }}</p>
                                <p class="card-text">{{ item.dob.age }}</p>
              
  </div>
</div>
  
</template>
<script>
import axios from "axios";
const urlUsers = "https://randomuser.me/api/?results=10";
export default {
  name: "randomuser",
  created() {
    this.getUsers();
  },
  data() {
    return {
      lists: null,
    };
  },
  methods: {
    getUsers() {
      axios
        .get(urlUsers)
        .then((response) => {
          this.lists = response.data.results;
        })
        .catch((e) => console.log(e));
    },
  },
};
</script>
<style lang="scss">
 #random{
   background: gray;

   .card-body{
     background: red;
     border: solid 1px yellow;
     margin: 1rem 1rem;
     padding: 1rem 1rem;

   }

   .card-title{
     background: gray;
   }
  
  .card-text{
     background: greenyellow;
   }

   .card-image{
     border-radius: 50%;
     border: 10px solid white;
   }
 
  }
</style>

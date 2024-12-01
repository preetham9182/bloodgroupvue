<template>
  <MyHeader appName="BLOOD GROUPS INFORMATION"/> 
  <BloodGroupsList :bloodGroups=bloodGroups />
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import BloodGroupsList from './components/BloodGroupsList.vue'


export default{
  name: 'App',
  components:{
    MyHeader,
    BloodGroupsList
  },
  data(){
    return {
      bloodGroups: []
    }
  },
  methods:{
    async fetchBloodGroupsList(){
      const res = await fetch('https://bloodgroups.onrender.com/api');
      const data = await res.json()
      return data.bloodGroups;
    }
  },
  async created(){
      this.bloodGroups = await this.fetchBloodGroupsList();
  }
}
</script>


<style>

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
html,body, #app{
  height: 100%;
}

body {
  font-family: sans-serif;
}

#app{
  background-color: lightgray;
}
</style>

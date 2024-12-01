<template>
    <div class="container">
        <table >
            <tbody>
                <tr>
                    <th class="heading">BLOOD TYPE</th>
                    <th class="heading">DONOR</th>
                    <th class="heading">RECIPIENT</th>
                    <th class="heading">PERSONALITY</th>
                    <th class="heading">% IN WORLD </th>
                </tr>
                <tr v-for="bloodGroup in bloodGroups" :key="bloodGroup.blood_type" >
                    <SingleBloodGroup :bloodGroup=bloodGroup />
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
import SingleBloodGroup from './SingleBloodGroup.vue';


export default {
    name: 'BloodGroupsList',
    props:{
        bloodGroups: Array
    },
    components:{
        SingleBloodGroup
    }
}

</script>
<style scoped>
.container{
    padding: 5rem;
}
table{
    margin: auto;
    border-collapse: separate;
    border-spacing: 0;
    white-space: normal;
    overflow: hidden;
    border: 1px solid darkgrey;
}
tr, th, td{
    padding: 10px 15px;
    text-align: left;
    border: 1px solid darkgrey;
    font-weight: 500;
}
tr:nth-child(1) {
    background-color: black !important;
    color: #fff;
}
tr:nth-child(odd) {
    background-color: cadetblue;
}
.heading{
    min-width: 100px;
    font-weight: bold;
}
</style>

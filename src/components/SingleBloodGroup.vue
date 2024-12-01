<template>
    <td>{{bloodGroup.blood_group}}</td>
                    <td>{{bloodGroup.donor}}</td>
                    <td>{{bloodGroup.recipient}}</td>
                    <td>{{bloodGroup.personality}}</td>
                    <td>{{bloodGroup.percentage_people_in_world}}</td>
</template>

<script>
    export default{
        name: 'SingleBloodGroup',
        props:{
            bloodGroup: Object
        }
    }
</script>

<style scoped>
td{
    padding: 10px 15px;
    text-align: left;
    border: 1px solid darkgrey;
    font-weight: 500;
}
</style>
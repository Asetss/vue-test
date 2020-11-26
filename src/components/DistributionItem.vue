<template>
    <tr>
        <th scope="row">{{ index }} </th>
        <td>{{ dist.number}}</td>
        <td>{{ dist.volume }} мг</td>
        <td>{{ dist.jam_type }}</td>
    </tr>
</template>

<script>
    export default {
        props: {
            dist: {
                type: Array,
                required: true
            },
            index: Number
        },


    }
</script>

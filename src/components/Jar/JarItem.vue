<template>
    <tr>
        <th scope="row">{{ index }} </th>
        <td>{{ jar.number}}</td>
        <td>{{ jar.volume }} мг</td>
    </tr>
</template>

<script>
export default {
  props: {
    jar: {
      type: Object,
      required: true
    },
    index: Number
  },

    
}
</script>

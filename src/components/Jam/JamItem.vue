<template>
    <tr>
        <th scope="row">{{ index }} </th>
        <td>{{ jam.type_jame}}</td>
        <td>{{ jam.volume }} мг</td>
        <td>
          <button class="btn btn-primary" v-on:click="distributeJam(jam, index)">
                  Распределить
          </button>
          
          </td>
    </tr>
</template>

<script>
export default {
  props: {
    jam: {
      type: Object,
      required: true
    },
    index: Number
  },

  methods: {

    distributeJam(jam, index) {
        jam.index = index;
        this.$emit('distribute-jam', jam)
    }
    
  }

    
}
</script>

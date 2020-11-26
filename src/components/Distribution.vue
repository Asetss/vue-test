<template>

<div class="card">
   <div>
      <h3>Распределенные варенья</h3>
      <table class="table table-hover">
         <thead>
         <tr>
            <th scope="col">#</th>
            <th scope="col">Номер банки</th>
            <th scope="col">Обьем банки</th>
            <th scope="col">Тип варенья</th>
         </tr>
         </thead>
         <tbody>
         <DistributionItem
                 v-for="(dist, i) of distData"
                 v-bind:dist="dist"
                 v-bind:key="dist.id"
                 v-bind:index="i"
         />
         </tbody>
      </table>
   </div>
</div>
</template>

<script>

   import DistributionItem from '@/components/DistributionItem'
   export default {
      props: {
         distData: {
            type: Array,
            required: true
         },
      },

      components: {
         DistributionItem
      }
   }
</script>

<style scoped>

.card {
    margin: 0 auto;
    float: none; 
    margin-bottom: 10px; 
}
</style>

<template>
  <form class="form-inline" @submit.prevent="onSubmit">
    
    <div class="form-group mb-2">
      <input type="text" class="form-control" v-model="number" placeholder="Номер банки">
    </div>

    <div class="form-group mx-sm-3 mb-2">
      <input type="text" class="form-control" v-model="volume" placeholder="Обьем банки">
    </div>

    <button type="submit" class="btn btn-success">Добавить</button>
</form>
  
</template>

<script>
export default {
  data() {
    return {
      number: '',
      volume:''
    }
  },
  methods: {
    onSubmit() {
    
        const newJar = {
          id: Date.now(),
          number: this.number,
          volume:  this.volume,
        }

        this.$emit('add-jar', newJar)
        this.number = ''
        this.volume = ''
      
    }
  }
}
</script>

<style scoped>

</style>
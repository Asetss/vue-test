<template>
  <form class="form-inline" @submit.prevent="onSubmit">
    
    <div class="form-group mb-2">
      <input type="text" class="form-control" v-model="type_jame" placeholder="Тип варенья">
    </div>

    <div class="form-group mx-sm-3 mb-2">
      <input type="text" class="form-control" v-model="volume" placeholder="Обьем варенья">
    </div>

    <button type="submit" class="btn btn-success">Добавить</button>
</form>
  
</template>

<script>
export default {
  data() {
    return {
      type_jame: '',
      volume:''
    }
  },
  methods: {
    onSubmit() {
    
        const newJam = {
          id: Date.now(),
          type_jame: this.type_jame,
          volume:  this.volume,
        }

        this.$emit('add-jam', newJam)
        this.type_jame = ''
        this.volume = ''
      
    }
  }
}
</script>

<style scoped>

</style>
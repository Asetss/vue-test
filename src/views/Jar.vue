<template>

  <div>
    <h3>Бабушкина варенья</h3>
   <div class="row">
      <div class="col-md-6">

        <h2>Пустые банки</h2>

        <hr>
        <AddJar
          @add-jar="addJar"
        />

          <JarList
            v-bind:jars="jars"
          />

      </div>
      <div class="col-md-6">
          <h2>Распределение варенья</h2>
          <hr>

        <AddJam
          @add-jam="addJam"
        />

          <JamList
            v-bind:jams="jams"
            @distribute-jam="distributeJam"
          />
      </div>

       <Distribution v-bind:distData="distData"/>
   </div>
  </div>

</template>


<script>
import JarList from '@/components/Jar/JarList'
import JamList from '@/components/Jam/JamList'
import AddJar from '@/components/Jar/AddJar'
import AddJam from '@/components/Jam/AddJam'
import Distribution from '@/components/Distribution'

export default {
    name: 'app',
    data() {
      return {
        jars: [],
        jams: [],
          distData: []
      }
    },

    mounted() {
      this.jars = [
        {id: 1, volume: 500, number: 'М85', occupied_vol: 0},
        {id: 2, volume: 500, number: 'М86', occupied_vol: 0},
        {id: 3, volume: 500, number: 'М87', occupied_vol: 0},
        {id: 4, volume: 1000, number: 'М88', occupied_vol: 0}
      ]

      this.jams = [
        {id: 1, type_jame: 'Абрикосовый', volume: 2000, occupied_vol: 2000},
        {id: 2, type_jame: 'Вишневый', volume: 1500, occupied_vol: 2000},
        {id: 3, type_jame: 'Смородина', volume: 300, occupied_vol: 2000},
        {id: 4, type_jame: 'Вишневый', volume: 700, occupied_vol: 2000},
        {id: 5, type_jame: 'Вишневый', volume: 1398, occupied_vol: 2000},
      ]
    },

    methods: {
      addJar(jar) {
         this.jars.push(jar)
      },

      addJam(jam) {
         this.jams.push(jam)
      },
      
      distributeJam(jam) {

        let jam_volume = jam.volume;
        for (const jar of this.jars) {
            const val = Math.min(jar.volume, jam_volume); 

            this.distData.push({
                  id: jar.id,
                  number: jar.number,
                  volume: val,
                  jam_type: jam.type_jame
            });

            jam_volume -= val;
            if (jam_volume === 0) break;
        }

         this.jams.splice(jam.index, 1);

      }
    },

  components: {
    JarList,
    JamList,
    AddJar,
    AddJam,
    Distribution
  }

}
</script>

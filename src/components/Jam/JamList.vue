<template>
    <div>
        <table class="table table-hover">
            <thead>
                <tr>
                <th scope="col">#</th>
                <th scope="col">Тип варенья</th>
                <th scope="col">Обьем</th>
                    <th scope="col"></th>
                </tr>
            </thead>
            <tbody>
                <JamItem
                v-for="(jam, i) of jams"
                    v-bind:jam="jam"
                    v-bind:key="jam.id"
                    v-bind:index="i"
                    v-on:distribute-jam="distributeJam"
                />
            </tbody>
            </table>
    </div>
</template>

<script>
import JamItem from '@/components/Jam/JamItem'
export default {

    props: ['jams'],

    components: {
        JamItem
    },

      methods: {
        distributeJam(jam) {
            this.$emit('distribute-jam', jam)
        }
    }  
}
</script>
<template>

    <div>
    <table class="table table-hover">
        <thead>
            <tr>
            <th scope="col">#</th>
            <th scope="col">Номер банки</th>
            <th scope="col">Обьем банки</th>
            </tr>
        </thead>
        <tbody>
            <JarItem
            v-for="(jar, i) of jars"
                v-bind:jar="jar"
                v-bind:key="jar.id"
                v-bind:index="i"
            />
        </tbody>
        </table>
    </div>
</template>

<script>
import JarItem from '@/components/Jar/JarItem'
export default {

    props: ['jars'],

    components: {
        JarItem
    }
    
}
</script>

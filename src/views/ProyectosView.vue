<template>
    <BarraSuperior></BarraSuperior>

    <main>
        <section>
            <p>Este es un conjunto de paginas que he maquetado o desarollado por mi propia cuenta</p>

            <Proyectos v-for="proyecto in proyectosExperiencia" v-bind="proyecto" :key="proyecto"></Proyectos>
        </section>

        <section>
            <p>Este es el conjunto de Mockups que he diseñado</p>

            <Proyectos v-for="mockup in mockups" v-bind="mockup" :key="mockup"></Proyectos>
        </section>

    </main>


    <BarraInferior></BarraInferior>
</template>

<script setup>
import BarraInferior from '../components/BarraInferior.vue';
import BarraSuperior from '../components/BarraSuperior.vue';
import proyectosExperiencia from '../experiencia/proyectosExperiencia';
import Proyectos from '../components/Proyectos.vue';
import mockups from '../experiencia/mockups';

</script>

<script>
export default {
    computed: {
        proyectosExperiencia() {
            return proyectosExperiencia
        },
        mockups() {
            return mockups
        }
    }
}
</script>

<style lang="scss" scoped>
main {
    padding: 50px 70px;

    * {
        font-family: 'Galyon';
    }
}

h2 {
    font-size: xx-large;
}

p {
    margin-bottom: 50px;
    background: #BC9DFF;
    padding: 10px;
    margin-top: 15px;
    font-size: 14px;
    font-style: italic;
}
</style>

<style lang="scss">
.proyeco-uno {
    margin-bottom: 100px;
}
</style>
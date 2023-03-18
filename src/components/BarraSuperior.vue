<template>
    <header class="container">
        <div class="row">

            <div class="nombre col-6">
                <h1><a href="/"> Yessenia Colocho </a></h1>
            </div>

            <nav v-if="viewName === 'home'" class="secciones col-6">
                <a href="#sobre-mi">Sobre Mi</a>
                <a href="#experiencia">Experiencia</a>
                <a href="#proyectos">Proyectos</a>
                <a href="#contactos">Contacto</a>
            </nav>
            <h3 v-else class="titulo-pagina col-6">
                {{ viewName }}
            </h3>

        </div>
    </header>
</template>

<script>
export default {
    computed: {
        viewName() {
            return this.$route.name
        }
    }
}
</script>

<style scoped lang="scss">
header {
    background: #462A5C;
    padding: 20px 50px !important;
}

.nombre {
    h1 {
        display: flex;
        align-items: center;
        font-family: "Philosopher";
        font-weight: normal;
        font-size: 35px;
        color: white;
        margin: 15px 0;

        &::before {
            content: '';
            background: #C376FF;
            width: 17px;
            height: 17px;
            display: inline-block;
            margin: 3px;
            border-radius: 100%;
            transform: translate(0, 3px);
        }

        a{
            color: inherit;
            &::before{
                display: none;
            } 
        }
    }
}

.secciones {
    display: flex;
    justify-content: flex-end;
    align-items: flex-end;

    a {
        font-family: 'Galyon';
        margin-left: 25px;
        color: white;
        font-size: small;

        &::before {
            background: #c376ff;
        }
    }
}

.titulo-pagina {
    text-align: right;
    text-transform: capitalize;
    color: white;
    padding: 0.5em;
}
</style>
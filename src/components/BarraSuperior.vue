<template>
    <header class="container">
        <div class="row">

            <div class="nombre col-6">
                <h1>Yessenia Colocho</h1>
            </div>

            <nav class="secciones col-6">
                <a href="#sobre-mi">Sobre Mi</a>
                <a href="#">Experiencia</a>
                <a href="#">Proyectos</a>
                <a href="#">Contacto</a>
            </nav>

        </div>
    </header>
</template>

<script setup>

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
</style>
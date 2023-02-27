<template>
    <header class="container">
        <div class="row entorno-entero">
            <div class="nombre col-6">
                <div class="redonda-texto">
                    Hecho por Yessenia Colocho en Barcelona
                </div>

                <div>
                    © Yessenia Colocho, {{ ano }}
                </div>
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

<script>
export default {
    computed: {
        ano() {
            return new Date().getFullYear()
        }
    }
}
</script>

<style scoped lang="scss">
header {
    background: #462A5C;
}

.entorno-entero {
    padding: 20px 30px;
    font-family: 'Galyon';

    .nombre {
        color: white;
        font-size: small;

        div {
            margin-bottom: 20px;
        }

        .redonda-texto {
            &::before {
                content: '';
                background: #2D1B3B;
                width: 11px;
                height: 11px;
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
        margin-bottom: 10px;

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
}
</style>
<template>
    <BarraSuperior></BarraSuperior>

    <main class="main">
        <section id="sobre-mi" class="elemento-superior">
            <div class="fotografia">
                <img src="atarashif.jpg" />
            </div>

            <div class="elemento-texto">
                <p class="texto">Excepteur eu ullamco sunt est dolore dolore ea. Labore qui ea ut sint consequat. Laboris
                    deserunt sint enim quis esse aliquip deserunt nisi voluptate enim sit culpa et voluptate. Reprehenderit
                    cillum occaecat veniam est sint. Cupidatat adipisicing tempor ad occaecat. Eiusmod sunt commodo proident
                    nisi laboris sint. Aute fugiat aliquip dolor Lorem officia nulla in pariatur aute non elit duis.</p>
            </div>

        </section>

        <section class="experiencia-y-redonda container">
            <div class="row">
                <div class="experiencia col-7">

                    <BarraExperiencia :key="barra.nombre" v-for="barra in barrasDeExperiencia" v-bind="barra">
                    </BarraExperiencia>

                </div>

                <div class="redonda col-5">

                    <div class="bordes-circulo"></div>

                    <div class="circulo">
                        <div class="arco"></div>
                        <div class="arco inferior"></div>
                        <p>
                            Nostrud deserunt commodo mollit magna reprehenderit ipsum aliqua cupidatat ipsum est duis non
                            laboris elit. Id aliquip nisi consectetur laboris nulla Lorem ex amet sunt consequat pariatur
                            adipisicing elit. Adipisicing labore deserunt in pariatur ea amet consectetur commodo. Qui duis
                            dolore non cupidatat exercitation velit. Lorem proident exercitation exercitation qui eiusmod ut
                            elit elit sit incididunt ea ad. Mollit occaecat eu voluptate enim aute labore et incididunt.
                            Cupidatat ex incididunt sint exercitation culpa sunt esse.
                        </p>
                    </div>

                </div>

            </div>

        </section>

        <section class="otros">
            <h4 class="linea-animada">
                Otros
            </h4>

            <div class="logos-otros">
                <div class="row">

                    <div class="lado-derecho col-4">
                        <div v-for="imagen in experienciaOtros.diseno">
                            <img :src="imagen" />
                        </div>
                    </div>

                    <div class="lado-medio col-4">
                        <div v-for="imagen in experienciaOtros.tecnologia">
                            <img :src="imagen" />
                        </div>
                    </div>

                    <div class="lado-izquierdo col-4">
                        <div v-for="imagen in experienciaOtros.otros">
                            <img :src="imagen" />
                        </div>
                    </div>

                </div>

            </div>

        </section>

        <section class="proyectos">


            <h3>Proyectos</h3>

            <div class="proyeco-uno container">
                <div class="row">
                    <div class="imagen-principal borde-esquina col-6">
                        <img src="aula-virtual-principal.png" />

                        <p>Aula Virtual</p>
                    </div>

                    <div class="imagenes-secundarias col-6">
                        <div>
                            <img src="aula-virtual-1.png" />
                        </div>
                        <div>
                            <img src="aula-virtual-2.png" />
                        </div>
                        <div>
                            <img src="aula-virtual-3.png" />
                        </div>


                    </div>
                </div>
            </div>

        </section>

        <section class="final-de-pagina">

            <div class="boton-final">
                <div class="borde-esquina-invertido">
                    <button>Todos los proyectos</button>
                </div>
            </div>
        </section>

        <section class="contactos">
            <div>
                <h4>Muchas gracias por llegar hasta aqui, puedes contactarme usando los siguientes <b>links</b></h4>
            </div>

            <div class="imagen-correo">
                <div>
                    <img src="correo.png" />
                </div>

                <div class="texto-correo">
                    <div>
                        Colocho.Yessenia@gmail.com
                    </div>

                    <div>
                        Linkeding / YesseniaColochoG
                    </div>

                </div>
            </div>
        </section>

        <BarraInferior></BarraInferior>


    </main>
</template>

<script setup>
import BarraSuperior from '../components/BarraSuperior.vue';
import BarraExperiencia from '../components/BarraExperiencia.vue';
import barrasDeExperienia from '../experiencia/barrasDeExperienia';
import experienciaOtros from '../experiencia/experienciaOtros';
import BarraInferior from '../components/BarraInferior.vue';
</script>

<script>
export default {
    computed: {
        barrasDeExperiencia() {
            return barrasDeExperienia
        },
        experienciaOtros() {
            return experienciaOtros
        }
    }
}
</script>


<style scoped lang="scss">
.elemento-superior {
    margin-top: 50px;
    display: flex;
    align-items: center;
    padding: 0 !important;

    .fotografia {
        height: 550px;
        overflow: hidden;
        width: 400px;
        transform: translateX(0%);
        animation: 2s imagenAparecer;

        img {
            height: 100%;
            width: 100%;
            object-fit: cover;

        }
    }

    .elemento-texto {
        width: calc(100%);
        background: linear-gradient(45deg, #C376FF 0%, #e3c4fb 50%, #C376FF, );
        height: fit-content;
        padding: 70px 320px;
        position: absolute;
        right: -200px;
        z-index: -1;
        transform: rotate(3deg);
        animation: 2s bloqueAparecer;

        p {
            font-family: 'Galyon';
            transform: rotate(-3deg);
            font-size: 13px;
        }
    }
}

section {
    padding: 0 50px !important;
}

.experiencia-y-redonda {
    margin-top: 100px;

    .experiencia {}

    .redonda {
        height: 0;
        position: relative;

        .circulo {
            height: 0;
            width: 130%;
            padding-bottom: 130%;
            background: linear-gradient(45deg, #C376FF 0%, #e3c4fb 50%, #C376FF, );
            border-radius: 100%;
            transform: translateY(-15%);
            position: relative;

            p {
                position: absolute;
                top: 50%;
                transform: translateY(-50%);
                width: 50%;
                margin-left: 20%;
            }

            .arco {
                animation: 4s infinite linear lineasRedondas;

                &.inferior {
                    animation: 6s infinite linear lineasRedondasInverso;
                }
            }
        }
    }
}

.otros {
    padding: 0 50px !important;
    margin-top: 110px;

    h4 {
        display: inline-block;
        font-family: 'Galyon';
        font-size: 25px;
        margin-bottom: 20px;
        color: revert;
        font-family: 'Galyon';

        &::before {
            background: #C376FF;
            height: 2px;
        }
    }

    .logos-otros {
        height: auto;
        width: 40%;

        >.row {
            height: 100%;

            >div {
                >div {
                    width: 50%;
                    padding-bottom: 50%;
                    position: relative;
                    overflow: hidden;

                    img {
                        width: 100%;
                        height: 100%;
                        padding: 10px;
                        object-fit: contain;
                        position: absolute;
                    }
                }
            }
        }

        .lado-derecho {
            display: flex;
            flex-wrap: wrap;
            align-items: start;
        }

        .lado-medio {
            display: flex;
            flex-wrap: wrap;
            align-items: start;
            border-left: 2px #2D1B3B solid;

        }

        .lado-izquierdo {
            display: flex;
            flex-wrap: wrap;
            align-items: start;
            border-left: 2px #2D1B3B solid;


        }
    }

}

.proyectos {
    margin-top: 70px;

    h3 {
        font-family: 'Galyon';
    }

    .proyeco-uno {
        margin-top: 30px;
        height: auto;

        .borde-esquina {

            &::after,
            &::before {
                border-color: #C376FF;
                border-width: 3px;
            }
        }

        .imagen-principal {
            img {
                width: 100%;
                padding: 20px;
            }

            p {
                padding-left: 20px;
                font-family: 'Galyon';
                margin: 0;
                margin-top: 10px;
            }
        }
    }

    .imagenes-secundarias {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        padding-top: 20px;

        div {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 70%;
            overflow: hidden;
            height: 110px;

            img {
                width: 100%;
            }
        }



    }
}

.final-de-pagina {
    margin-top: 45px;

    .boton-final {
        background: linear-gradient(45deg, #C376FF 0%, #e3c4fb 50%, #C376FF, );
        width: 35%;
        height: 100px;
        transform: rotate(3deg);
        position: relative;
        left: -70px;
        display: flex;
        justify-content: center;
        align-items: center;

        >div {
            transform: rotate(-4deg);

            button {
                padding: 15px;
                font-family: 'Galyon';
                font-size: 13px;
                background: none;

                &::before {
                    content: '';
                    background: #C376FF;
                    width: 7px;
                    height: 7px;
                    display: inline-block;
                    margin: 3px;
                    border-radius: 100%;
                    transform: translate(0, 3px);
                }
            }
        }
    }
}

.contactos {
    margin-top: 110px;
    padding: 0 !important;
    position: relative;

    &::before {
        content: '';
        position: absolute;
        width: 60%;
        border-top: 3px #BC9DFF solid;
        top: 0;
    }

    h4 {
        padding: 30px;
        text-align: right;
        font-size: medium;
        font-family: 'Galyon';
    }

    .imagen-correo {
        margin-top: 70px;
        margin-bottom: 50px;
        display: flex;
        justify-content: center;
    }

    img {
        width: 300px;
    }

    .texto-correo {
        margin-top: 30px;
        font-family: 'Galyon';
        font-size: 15px;

        div {
            margin-bottom: 17px;
        }

    }
}






@keyframes imagenAparecer {
    0% {
        transform: translateX(-100%);
    }

    30% {
        transform: translateX(-100%);
    }

    100% {
        transform: translateX(0%);
    }
}

@keyframes bloqueAparecer {
    0% {
        transform: translateX(-40%) rotate(3deg);
        opacity: 0;
    }

    30% {
        transform: translateX(-40%) rotate(3deg);
        opacity: 0;
    }

    50% {
        opacity: 0;
    }

    100% {
        transform: translateX(0%) rotate(3deg);
        opacity: 1;
    }
}

@keyframes lineasRedondas {
    0% {
        transform: rotate(0deg) skewX(30deg);
    }

    100% {
        transform: rotate(360deg) skewX(30deg);
    }
}

@keyframes lineasRedondasInverso {
    0% {
        transform: rotate(360deg) skewX(30deg) scale(1.05);
    }

    100% {
        transform: rotate(0deg) skewX(30deg) scale(1.05);
    }
}
</style>


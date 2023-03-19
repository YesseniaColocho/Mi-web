<template>
    <BarraSuperior></BarraSuperior>

    <main class="main">
        <section id="sobre-mi" class="elemento-superior">
            <div class="fotografia">
                <img src="tarashif.jpg" />
            </div>

            <div class="elemento-texto">
                <p class="texto">
                    ¡Mi nombre es <strong> Yessenia Colocho</strong>!<br>
                    <br>
                    <strong>Soy una maquetadora y diseñadora UX y Web. </strong><br>
                    <br>
                    Estudié diseño publicitario y llevo este último año ampliando mis conocimientos y metiéndome a fondo en
                    el campo del desarrollo web.
                    Mis especialidades engloban el diseño enfocado a UX de interfaces y aplicaciones, así como el maquetado
                    de las mismas, con tecnologías como Figma, Adobe Illustrator, HTML, CSS, Node y Vue.
                    Me gusta el trabajo en equipo y ampliar mis conocimientos en el ámbito laboral, colaborando en proyectos
                    interesantes.<br>
                    <br>
                    Si quieres saber más… ¡Sigue bajando!
                </p>
            </div>

        </section>

        <section id="experiencia" class="experiencia-y-redonda container">
            <div class="row">
                <div class="experiencia col-7 ocultar">

                    <BarraExperiencia :key="barra.nombre" v-for="barra in barrasDeExperiencia" v-bind="barra">
                    </BarraExperiencia>

                </div>

                <div class="redonda col-5">

                    <div class="bordes-circulo"></div>

                    <div class="circulo ocultar-derecha">
                        <div class="arco"></div>
                        <div class="arco inferior"></div>
                        <p>
                            Mis estudios son diversos, pero siempre enfocados al diseño. Realicé mis estudios superiores de
                            Diseño publicitario en la escuela EAM - Leandre Cristòfol, Lleida, en 2018.<br><br>
                            Durante el curso manejé el uso del paquete Adobe, en especial Illustrator y Photoshop. Las leyes
                            y propiedades del color, lettering, maquetación y layouting, con el fin de proporcionar
                            productos atractivos y comunicativos, en una multitud de ámbitos profesionales y
                            sectores.<br><br>
                            Partiendo de estos conocimientos, expandí mi abanico formándome en diseño web enfocado al UX/UI.
                            En el camino aprendí a utilizar herramientas de Mockup como Figma, para realizar diversos
                            prototipos de aplicaciones.<br><br>
                            Luego, he ido aprendiendo y dominando el desarrollo web. Primero con HTML5 y CSS3 (también
                            supersets como SCSS), maquetando diversos tipos de webs y aplicaciones. Expandiendo estas
                            habilidades, profundicé en el estudio de Frameworks de Node, en concreto Vue. Sabiendo trabajar
                            en este entorno.<br><br>
                            En estos momentos, me sigo formando en JS, PHP, React y Wordpress, para en un futuro, añadirlos
                            a mí curriculum.
                        </p>
                    </div>

                </div>

            </div>

        </section>

        <section class="otros ocultar">
            <h4 class="linea-animada">
                Otros
            </h4>

            <div class="logos-otros">
                <div class="row">

                    <div class="lado-derecho col-4">
                        <ExperienciaInfo v-for="experiencia in experienciaOtros.diseno" v-bind="experiencia">
                        </ExperienciaInfo>
                    </div>

                    <div class="lado-medio col-4">
                        <ExperienciaInfo v-for="tecnologia in experienciaOtros.tecnologia" v-bind="tecnologia">
                        </ExperienciaInfo>
                    </div>

                    <div class="lado-izquierdo col-4">
                        <ExperienciaInfo v-for="otro in experienciaOtros.otros" v-bind="otro"></ExperienciaInfo>
                    </div>

                </div>

            </div>

        </section>

        <section id="proyectos" class="proyectos ocultar-abajo">

            <h3>Proyectos</h3>

            <Proyectos v-for="proyecto, index in proyectosHome" v-bind="proyecto" :key="`${index}-${proyecto.titulo}`">
            </Proyectos>

        </section>

        <section class="final-de-pagina">

            <div class="boton-final">
                <div class="borde-esquina-invertido">
                    <a href="/proyectos">Todos los proyectos</a>
                </div>
            </div>
        </section>

        <section id="contactos" class="contactos">
            <div>
                <h4>Muchas gracias por llegar hasta aqui, puedes contactarme usando los siguientes <b>links</b></h4>
            </div>

            <div class="imagen-correo ocultar">
                <div>
                    <img src="/correo.png" />
                </div>

                <div class="texto-correo">
                    <div>
                        <a href="mailto:colocho.yessenia@gmail.com">Colocho.Yessenia@gmail.com</a>
                    </div>

                    <div>
                        <a href="https://www.linkedin.com/in/yessenia-colocho-330654160/" target="_blank"> Linkedin /
                            Yessenia Colocho</a>
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
import Proyectos from '../components/Proyectos.vue';
import proyectosExperiencia from '../experiencia/proyectosExperiencia';
import ExperienciaInfo from '../components/ExperienciaInfo.vue';
</script>

<script>
export default {
    computed: {
        barrasDeExperiencia() {
            return barrasDeExperienia;
        },
        experienciaOtros() {
            return experienciaOtros;
        },
        proyectosHome() {
            return proyectosExperiencia.filter((proyecto) => proyecto.mostrarEnHome === true)
        }
    },
    components: { Proyectos, ExperienciaInfo, ExperienciaInfo },

    created() {
        window.addEventListener('scroll', this.handleScroll);
    },
    unmounted() {
        window.removeEventListener('scroll', this.handleScroll);
    },
    methods: {
        handleScroll() {
            console.log(window.scrollY)
            let experiencia = 300
            if (experiencia < window.scrollY) {
                document.querySelector('.experiencia').classList.remove("ocultar");
                document.querySelector('.circulo').classList.remove("ocultar-derecha");
            }
            let otro = 850
            if (otro < window.scrollY) {
                document.querySelector('.otros').classList.remove('ocultar')
            }
            let proyectos = 1200
            if (proyectos < window.scrollY) {
                document.querySelector('.proyectos').classList.remove('ocultar-abajo')
            }
            let correo = 2500
            if (correo < window.scrollY) {
                document.querySelector('.imagen-correo').classList.remove('ocultar')
            }
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
            font-size: 14px;
        }
    }
}

section {
    padding: 0 50px !important;
}

.experiencia-y-redonda {
    margin-top: 100px;

    .experiencia {
        transition: all 0.8s;
    }

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
            transition: all 0.8s;

            p {
                position: absolute;
                top: 50%;
                transform: translateY(-50%);
                width: 55%;
                margin-left: 20%;
                font-size: small;
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
    transition: all 0.8s;

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
                    position: relative;
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
    transition: all 0.8s;

    h3 {
        font-family: 'Galyon';
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

            a {
                padding: 15px;
                font-family: 'Galyon';
                font-size: 13px;
                background: none;
                color: black;
                display: inherit;

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
        transition: all 0.8s;
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

.ocultar {
    opacity: 0;
    transform: translateX(-10%);
}

.ocultar-derecha {
    opacity: 0;
    transform: translateX(10%) !important;
}

.ocultar-abajo {
    opacity: 0;
    transform: translateY(10%) !important;
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

<style lang="scss">
.proyeco-uno {
    margin-bottom: 80px;

    &:nth-child(odd) {
        .row {
            flex-direction: row-reverse;
        }
    }
}
</style>


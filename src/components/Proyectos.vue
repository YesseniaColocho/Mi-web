<template>
    <div class="proyeco-uno container">
        <div class="row">
            <div class="imagen-principal borde-esquina col-6">
                <img :src='imagenPrincipal' @click="irA(link)" />

                <a :href="link" target="_blank">{{ titulo }}</a>
                <p class="descripcion" v-if="descripcion">{{ descripcion }}</p>
            </div>

            <div class="imagenes-secundarias col-6">

                <div v-for="imagen, index in imagenes.slice(0, 2)" :class="{ 'activo': imagenActivaCarrusel === index }"
                    @mouseover="manejarHover(index)" @mouseleave="hover = false" @click="irA(link)">
                    <img :src="`/${imagen}`" />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            imagenActivaCarrusel: 0,
            numeroMaximoPaginas: 2,
            hover: false
        }
    },
    props: {
        titulo: {
            type: String, required: true
        },
        imagenPrincipal: {
            type: String, required: true
        },
        imagenes: {
            type: Array, required: true
        },
        descripcion: {
            type: String
        },
        link: {
            type: String
        }
    },
    mounted() {
        setInterval(() => {
            let paginaSiguiente = this.imagenActivaCarrusel + 1
            if (paginaSiguiente >= this.numeroMaximoPaginas) {
                paginaSiguiente = 0
            }
            if (this.hover === false) {
                this.cambioPagina(paginaSiguiente)
            }
        }, 5000)
    },
    methods: {
        manejarHover(numeroPagina) {
            this.hover = true
            this.cambioPagina(numeroPagina)
        },
        cambioPagina(numeroPagina) {
            this.imagenActivaCarrusel = numeroPagina
        },
        irA(link) {
            window.open(link, '_blank');

        }
    }
}
</script>

<style scoped lang="scss">
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
            cursor: pointer
        }

        a {
            color: inherit;
            padding-left: 20px;
            display: inline-block
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
        height: 50%;
        opacity: 0.5;
        transform: scale(0.9);
        cursor: pointer;
        transition: all 1s;

        &.activo {
            opacity: 1;
            transform: scale(1);
        }

        img {
            width: 100%;
            box-shadow: 5px 5px 18px #00000021;
        }
    }
}

.descripcion {
    font-size: 14px;
    padding: 0 20px 20px 0;
}
</style>
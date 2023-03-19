<template>
    <div class="barra-experiencia">
        <div class="logo">
            <img :src="`/${imagen}`" />
        </div>

        <div class="barra">
            <div>
                <h3>{{ nombre }}</h3>
                <p>{{ subtitulo }}</p>
            </div>

            <div class="barra-experiencia">

                <div :style="`width: ${porcentaje}%;`" class="valor">

                </div>

            </div>

        </div>

    </div>
</template>

<script>

export default {
    name: 'BarraExperiencia',
    props: {
        nombre: {
            type: String
        },
        subtitulo: {
            type: String
        },
        imagen: {
            type: String
        },
        porcentaje: {
            type: Number
        }
    }
}
</script>

<style scoped lang="scss">
.barra-experiencia {
    display: flex;

    >* {
        display: flex;
    }

    .logo {
        width: 10%;


        img {
            width: 100%;
            object-fit: contain;
            padding: 10px;
            margin: 20px 0;
        }
    }

    .barra {
        padding: 20px;
        width: 85%;
        display: inline-flex;
        flex-direction: column;
        justify-content: center;
        margin-left: 15px;

        h3 {
            font-size: 20px;
            margin: 0;
            font-family: 'Galyon';
            font-size: 20px;
        }

        p {
            margin: 0;
            font-family: 'Galyon';
            font-size: small;


        }
    }

    .barra-experiencia {
        background: #E2BCFF;
        height: 25px;
        margin-top: 5px;
        border-radius: 50px;
        overflow: hidden;
        width: 70%;

        .valor {
            background: #C376FF;
            height: 105%;
            display: inline-block;
            position: relative;
        }
    }
}
</style>
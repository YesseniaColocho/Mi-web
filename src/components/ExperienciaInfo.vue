<template>
    <div class="experiencia-info">

        <div @mouseover="hover = true" @mouseleave="hover = false" class="logo">
            <img :src="`/${img}`" />
        </div>

        <Transition>
            <div v-if="hover" class="ficha" @mouseover="hover = true" @mouseleave="hover = false">
                <div class="uno">
                    <img :src="`/${img}`" />
                </div>

                <div class="dos">
                    <h3>{{ titulo }}</h3>

                    <p>{{ descripcion }}</p>
                </div>

            </div>
        </Transition>


    </div>
</template>

<script>
export default {
    data() {
        return {
            hover: false
        }
    },
    props: {
        titulo: { type: String },
        descripcion: { type: String },
        img: { type: String },
    }
}
</script >


<style scoped lang="scss">
.experiencia-info {
    .logo {
        width: 100%;
        padding-bottom: 100%;
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

    .ficha {
        position: absolute;
        z-index: 1;
        width: 500px;
        background: white;
        border: #e3c4fb 1px solid;
        display: flex;
        padding: 10px;
        align-items: center;

        * {
            font-family: 'Galyon';
        }

        box-shadow: 2px 2px 2px rgba($color: #000000, $alpha: 0.15);
        transform: translateX(10px);

        .uno {
            width: 20%;

            img {
                width: 100%;
                padding: 20px
            }
        }

        .dos {
            width: 80%;

            h3 {
                font-size: large;
            }

            p {
                font-size: small;
            }
        }
    }
}






.v-enter-active,
.v-leave-active {
    transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
    opacity: 0;
}</style>
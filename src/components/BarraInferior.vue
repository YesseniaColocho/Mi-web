<template>
  <footer class="container">
    <div class="row entorno-entero">
      <div class="nombre col-12">
        <div class="redonda-texto">Hecho por Yessenia Colocho en Barcelona</div>

        <div>© Yessenia Colocho, {{ ano }}</div>
      </div>

      <nav v-if="false" class="secciones col-6">
        <a class="line" href="#sobre-mi">Sobre Mi</a>
        <a class="line" href="#experiencia">Experiencia</a>
        <a class="line" href="#proyectos">Proyectos</a>
        <a class="line" href="#contactos">Contacto</a>
      </nav>
    </div>
  </footer>
</template>

<script>
export default {
  computed: {
    ano() {
      return new Date().getFullYear();
    },
  },
};
</script>

<style scoped lang="scss">
footer {
  position: absolute;
  bottom: 0;
  background: transparent;
}

.entorno-entero {
  padding: 0 30px;
  font-family: "Galyon";

  .nombre {
    display: flex;
    justify-content: space-between;
    color: #462a5c;
    font-size: small;

    div {
      margin-bottom: 20px;
    }

    .redonda-texto {
      &::before {
        content: "";
        background: #2d1b3b;
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
      font-family: "Galyon";
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

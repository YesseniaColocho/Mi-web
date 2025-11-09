<template>
  <main class="main">
    <div class="sidebar">
      <h1>Yessenia Colocho</h1>
      <h2>Desarrolladora y diseñadora web</h2>
      <ul>
        <li><a href="/proyectos" target="_blank">Proyectos</a></li>
        <li>
          <a
            href="https://drive.google.com/file/d/1uE6iykdPGyEq4M6ySwZQAq-oUGImcFUf/view?usp=drive_link"
            target="_blank"
            >Currículum</a
          >
        </li>
        <li @click="toggleContacto">Contacto</li>
      </ul>
    </div>
    <div class="float-text">Página web en reconstrucción</div>
  </main>
  <BarraInferior></BarraInferior>

  <Transition>
    <div v-if="contactoVisible" class="card">
      <button class="close-button" @click="toggleContacto">X</button>
      <h1>Contacto</h1>

      <ul>
        <li>
          <a class="line" href="mailto:colocho.yessenia@gmail.com">
            <b>Email</b>: Colocho.Yessenia@gmail.com</a
          >
        </li>

        <li>
          <a
            class="line"
            href="https://www.linkedin.com/in/yessenia-colocho-330654160/"
            target="_blank"
          >
            <b>Linkedin</b>: Yessenia Colocho</a
          >
        </li>
      </ul>
    </div>
  </Transition>
</template>

<script setup>
import { ref, Transition } from "vue";
import BarraInferior from "../components/BarraInferior.vue";

const contactoVisible = ref(false);

function toggleContacto() {
  contactoVisible.value = !contactoVisible.value;
}
</script>

<script setup></script>

<style scoped lang="scss">
$shadowColor: rgba(0, 0, 0, 0.355);

main {
  height: 100vh;
  background: #ffffff;
  background: linear-gradient(
    170deg,
    rgba(255, 255, 255, 1) 0%,
    rgba(255, 255, 255, 1) 57%,
    rgba(222, 189, 255, 1) 100%
  );
}

footer {
  text-shadow: 10px 10px 4px $shadowColor;
}
ul {
  margin-top: 5px;
  padding-left: 10px;
  li {
    margin-top: 10px;
    list-style: none;
  }
}

a {
  color: grey;
  transition: all 0.5s ease;
  &:hover {
    color: #646cff;
  }
}

.sidebar {
  padding: 30px;
  text-shadow: 5px 5px 4px $shadowColor;
  width: 300px;

  h1 {
    font-size: 1.7em;
    font-family: Philosopher;
  }
  ul {
    margin-top: 30px;
    padding: 0;
  }
  h2,
  li {
    color: grey;
    font-size: 0.8em;
    transition: all 0.5s ease;
    width: fit-content;
  }
  li {
    cursor: pointer;
    &:hover {
      color: #646cff;
      transform: translate(-5px, -5px);
      text-shadow: 15px 15px 6px $shadowColor;
    }
  }
}

.float-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-60%, -60%);
  text-shadow: 30px 30px 6px $shadowColor;
}

.card {
  position: absolute;
  top: 120px;
  left: 150px;
  box-shadow: 20px 20px 30px $shadowColor;
  font-size: 0.9em;
  h1 {
    font-size: 1.2em;
  }

  a {
    color: #646cff;
  }

  .close-button {
    position: absolute;
    top: 10px;
    right: 10px;
    background-color: transparent;
  }
}

.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>

<template>
    <div>
        <!-- Botón de hamburguesa con clase dinámica -->
        <button @click="toggleMenu" :class="{ 'hamburger': true, 'white-icon': isOpen }">
            &#9776;
        </button>

        <!-- Menú desplegable -->
        <nav :class="{ open: isOpen }" class="side-menu">
            <RouterLink to="/" @click="closeMenu">Home</RouterLink>
            <RouterLink to="/about" @click="closeMenu">About</RouterLink>
        </nav>

        <!-- Fondo oscuro para cerrar el menú al hacer clic fuera -->
        <div v-if="isOpen" class="overlay" @click="closeMenu"></div>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import { RouterLink } from 'vue-router'

// Estado para controlar la visibilidad del menú
const isOpen = ref(false)

// Funciones para abrir/cerrar el menú
const toggleMenu = () => {
    isOpen.value = !isOpen.value
}

const closeMenu = () => {
    isOpen.value = false
}
</script>

<style scoped>
.hamburger {
    font-size: 24px;
    cursor: pointer;
    background: none;
    border: none;
    position: fixed;
    top: 10px;
    left: 10px;
    z-index: 1000;
    color: black;
    /* Color por defecto del icono */
    transition: color 0.3s;
    /* Transición suave para el cambio de color */
}

.white-icon {
    color: white;
    /* Color del icono cuando el menú está abierto */
}

.side-menu {
    position: fixed;
    top: 0;
    left: -250px;
    width: 250px;
    height: 100%;
    background-color: #333;
    padding-top: 60px;
    transition: 0.3s;
    z-index: 999;
}

.side-menu a {
    padding: 10px 15px;
    text-decoration: none;
    font-size: 18px;
    color: white;
    display: block;
    transition: 0.3s;
}

.side-menu a:hover {
    background-color: #575757;
}

.side-menu.open {
    left: 0;
}

.overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 500;
}
</style>
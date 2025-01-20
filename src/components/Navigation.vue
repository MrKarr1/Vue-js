<script setup>
import { ref } from 'vue';
import AboutSection from '../components/AboutSection.vue';
import ProjectList from '../components/ProjectList.vue';
import SkillBadge from '../components/SkillBadge.vue';
import Home from './Home.vue';

const showNav = ref(false);
setTimeout(() => { showNav.value = true; }, 1);

</script>


<template>
    <section>
        <transition name="nav-transition">
            <nav v-if="showNav" class="navigation">
                <button @click="$emit('nav', Home)"><i class="fa-solid fa-house"></i></button>
                <button @click="$emit('nav', AboutSection)">À propos</button>
                <button @click="$emit('nav', ProjectList)">Projets</button>
                <button @click="$emit('nav', SkillBadge)">Compétances</button>
            </nav>
        </transition>
    </section>
</template>

<style scoped>
.navigation {
    background: rgb(51, 51, 51);
    background: linear-gradient(90deg, rgba(51, 51, 51, 1) 0%, rgba(16, 78, 80, 1) 50%, rgba(51, 51, 51, 1) 100%);
    border-radius: 12px;
    padding: 15px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
    text-align: left;
}

.nav-transition-enter-active {
    transition: transform 2s cubic-bezier(0.25, 0.8, 0.25, 1), opacity 2s cubic-bezier(0.25, 0.8, 0.25, 1);
}

.nav-transition-enter-from {
    transform: translateY(-100%);
    opacity: 0;
}

.nav-transition-enter-to {
    transform: translateY(0);
    opacity: 1;
}

.component {
    margin-top: 5%;
}

button {
    background: none;
    border: none;
    color: inherit;
    font: inherit;
    cursor: pointer;
}

button:hover {
    color: black;
}
</style>
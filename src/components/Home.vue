<script setup>

import { ref } from 'vue';
const showtimerh1 = ref(false);
const showtimerimg1 = ref(false);
const showtimerimg2 = ref(false);


setTimeout(() => { showtimerh1.value = true; }, 500);
setTimeout(() => { showtimerimg1.value = true; }, 1000);
setTimeout(() => { showtimerimg2.value = true; }, 1500);


</script>



<template>
    <section>
        <div class="container-fluid">
            <div class="row">
                <div class="col-md-12">
                    <transition name="top">
                        <div class="card h-100" v-if="showtimerh1">
                            <div class="card-body">
                                <h1 class="card-text">Bienvenue Sur Le Site De Mon Projet De Web Développeur</h1>
                            </div>
                        </div>
                    </transition>
                </div>
                <div class="col-md-3"></div>
                <div class="col-md-6">
                    <transition name="top">
                        <div class="card h-100" v-if="showtimerh1">
                            <div class="card-body">
                                <h2>Liste de projets</h2>
                            </div>
                        </div>
                    </transition>
                </div>
                <div class="col-md-3"></div>
                <div class="col-md-6">
                    <transition name="slide-left">
                        <div class="card h-100" v-if="showtimerimg1">
                            <div class="card-body">
                                <div class="container-img">
                                    <img class="card-img" src="../picture/pong.png" alt="">
                                </div>
                                <p>Jeux Pong</p>
                            </div>
                        </div>
                    </transition>
                </div>
                <div class="col-md-6">
                    <transition name="slide-right">
                        <div class="card h-100" v-if="showtimerimg1">
                            <div class="card-body">
                                <div class="container-img">
                                    <img class="card-img" src="../picture/mvc.png" alt="">
                                </div>
                                <p>Blog de News</p>
                            </div>
                        </div>
                    </transition>
                </div>
                <div class="col-md-6">
                    <transition name="slide-left">
                        <div class="card h-100" v-if="showtimerimg2">
                            <div class="card-body">
                                <div class="container-img">
                                    <img class="card-img" src="../picture/doomsday-style-7715286_640.jpg" alt="">
                                </div>
                                <p>Titre</p>
                            </div>
                        </div>
                    </transition>
                </div>
                <div class="col-md-6">
                    <transition name="slide-right">
                        <div class="card h-100" v-if="showtimerimg2">
                            <div class="card-body">
                                <div class="container-img">
                                    <img class="card-img" src="../picture/doomsday-style-7715286_640.jpg" alt="">
                                </div>
                                <p>Titre</p>
                            </div>
                        </div>
                    </transition>
                </div>
            </div>
        </div>





        <div class="vide"></div>
    </section>
</template>


<style scoped>
.vide {
    margin-bottom: 300px;
}

section {
    text-align: center;
}

p {
    margin-top: 5px;
}

.container-fluid {
    margin-top: 50px;
}

.col-md-6 {
    margin-top: 50px;
    margin-bottom: 50px;
}

.card {
    background: rgb(51, 51, 51);
    background: linear-gradient(90deg, rgba(51, 51, 51, 1) 0%, rgba(16, 78, 80, 1) 50%, rgba(51, 51, 51, 1) 100%);
    border-radius: 12px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
    color: white;
}

.container-img {
    overflow: hidden;
    border-radius: 25px;
}

.card-img {
    border-radius: 25px;
    transition: transform 0.5s ease;
}

.card-img:hover {
    transform: scale(1.2);
}

/* Animation */
.top-enter-active {
    transition: opacity 1s ease;
}

.top-enter-from {
    opacity: 0;
}

.top-enter-to {
    opacity: 1;
}

/* Animation */
.slide-right-enter-active {
    transition: transform 2s cubic-bezier(0.25, 0.8, 0.25, 1), opacity 2s cubic-bezier(0.25, 0.8, 0.25, 1);
}

.slide-right-enter-from {
    transform: translateX(100%);
    opacity: 0;
}

.slide-right-enter-to {
    transform: translateX(0);
    opacity: 1;
}

.slide-left-enter-active {
    transition: transform 2s cubic-bezier(0.25, 0.8, 0.25, 1), opacity 2s cubic-bezier(0.25, 0.8, 0.25, 1);
}

.slide-left-enter-from {
    transform: translateX(-100%);
    opacity: 0;
}

.slide-left-enter-to {
    transform: translateX(0);
    opacity: 1;
}
</style>

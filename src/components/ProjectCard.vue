<script setup>
import ProjectList from './ProjectList.vue';
const props = defineProps(['projetprop'])
//console.log(props.projetprop);

</script>


<template>
    <section>
        <div class="container-fluid">
            <div class="row">
                <div class="clol-md-1"></div>
                <div class="clol-md-10">
                    <div class="card">
                        <div class="card-body">
                            <button @click="$emit('nav', ProjectList)">Retour</button>
                            <h2 class="card-title">{{ props.projetprop.titre }}</h2>
                            <p class="card-text description ">{{ props.projetprop.description }}</p>
                            <img :src="props.projetprop.image" class="card-img" />
                            <p class="card-text lorem">{{ props.projetprop.lorem }}</p>
                        </div>
                    </div>
                </div>
                <div class="clol-md-1"></div>
            </div>
        </div>
        <div class="vide"></div>
    </section>
</template>


<style scoped>
.vide {
    margin-bottom: 300px;
}

.container-fluid {
    margin-top: 50px;
}

.card {
    background: rgb(51, 51, 51);
    background: linear-gradient(90deg, rgba(51, 51, 51, 1) 0%, rgba(16, 78, 80, 1) 50%, rgba(51, 51, 51, 1) 100%);
    border-radius: 12px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
    color: white;
}

.card-img {
    border-radius: 50px;
}

.lorem {
    margin-top: 25px;
}

button {
    background: aliceblue;
    color: black;
    border-radius: 5px;
    border: none;
    font: inherit;
    cursor: pointer;
    margin-bottom: 15px;
}

button:hover {
    color: aliceblue;
    background: black;
}
</style>
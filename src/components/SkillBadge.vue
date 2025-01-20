<script setup>
import { ref } from 'vue';
const competences = ref([
    {
        id: 1,
        titre: "HTML",
        image: "../picture/html.png",
        description: "Langage de balisage pour créer des pages web.",
        niveau: 60
    },
    {
        id: 2,
        titre: "CSS",
        image: "../picture/css.png",
        description: "Langage de style pour la présentation des pages web.",
        niveau: 40  },
    {
        id: 3,
        titre: "PHP",
        image: "../picture/php.png",
        description: "Langage de programmation pour le développement web côté serveur.",
        niveau: 35    },
    {
        id: 4,
        titre: "JS",
        image: "../picture/js.png",
        description: "Langage de programmation pour le web.",
        niveau: 25
    },
    {
        id: 5,
        titre: "Vue.js",
        image: "../picture/vue.js.png",
        description: "Framework JavaScript pour le développement d'interfaces utilisateur interactives.",
        niveau: 20
    }
]);

</script>

<template>
    <section>
        <div class="container-fluid">
        <div class="row">
            <div v-for="competence in competences" :key="competence.id" class="col-md-12">
                <div class="card">
                    <div class="card-body">
                        <div class="competences">
                            <h6 class="card-title">{{ competence.titre }}</h6>
                            <img class="competences-image" :src="competence.image" :alt="competence.titre">
                            <p>{{ competence.description }}</p>
                            <div class="padding">
                                <div class="progress">
                                    <div class="progress-bar" role="progressbar"
                                        :style="{ width: competence.niveau + '%' }" :aria-valuenow="competence.niveau"
                                        aria-valuemin="0" aria-valuemax="100">{{
                                            competence.niveau }}%</div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    </section>
</template>

<style scoped>
.container-fluid{
    margin-top: 50px;
}
.card {
    background: rgb(51, 51, 51);
    background: linear-gradient(90deg, rgba(51, 51, 51, 1) 0%, rgba(16, 78, 80, 1) 50%, rgba(51, 51, 51, 1) 100%);
    border-radius: 12px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
    color: white;
}

.competences {
    text-align: center;
}

.col-md-12 {
    margin-bottom: 25px;
    padding-left: 15%;
    padding-right: 15%;
}

.competences-image {
    max-width: 100%;
    height: 50px;
    border-radius: 12px;
    margin-bottom: 15px;
}

.card-title {
    font-weight: bold;
}

.card-text {
    margin: 0;
}

.progress {
    height: 20px;
    margin-top: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);

}

.progress-bar {
    background-color: #333;
}
.padding{
padding-left: 25%;
padding-right: 25%;
}
</style>

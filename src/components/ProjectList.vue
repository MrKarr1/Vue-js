<script setup>
import { ref, computed, } from 'vue';
import ProjectCard from './ProjectCard.vue';

const projets = ref([
    {
        id: 1,
        titre: "Projet Jeux Pong",
        description: "Une application Jeu de Pong créé avec du JavaScript, utilisant des fonctions et des conditions pour faire rebondir la balle. Une simple IA est implémentée, qui suit les coordonnées de la balle.",
        image: "../picture/pong.png",
        lorem: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed. Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed. Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed."
    },
    {
        id: 2,
        titre: "Projet Blog News",
        description: "Un projet de création avec utilisation du modèle MVC, sans framework, dans le cadre de ma formation, pour ajouter, supprimer, modifier et consulter des articles liés à une base de données.",
        image: "../picture/mvc.png",
        lorem: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed. Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed. Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed."

    },
    {
        id: 3,
        titre: "Applications",
        description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. At autem possimus officiis, eum molestias, voluptas quod nihil voluptatem praesentium facere quos eveniet laboriosam eius numquam neque voluptates, suscipit sequi est.",
        image: "../picture/doomsday-style-7715286_640.jpg",
        lorem: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed. Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed. Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed."

    },
    {
        id: 4,
        titre: "lorem",
        description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. At autem possimus officiis, eum molestias, voluptas quod nihil voluptatem praesentium facere quos eveniet laboriosam eius numquam neque voluptates, suscipit sequi est.",
        image: "../picture/doomsday-style-7715286_640.jpg",
        lorem: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed. Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed. Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed."

    },
    {
        id: 5,
        titre: "lorem",
        description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. At autem possimus officiis, eum molestias, voluptas quod nihil voluptatem praesentium facere quos eveniet laboriosam eius numquam neque voluptates, suscipit sequi est.",
        image: "../picture/doomsday-style-7715286_640.jpg",
        lorem: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed. Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed. Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed."

    },
    {
        id: 6,
        titre: "lorem",
        description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. At autem possimus officiis, eum molestias, voluptas quod nihil voluptatem praesentium facere quos eveniet laboriosam eius numquam neque voluptates, suscipit sequi est.",
        image: "../picture/doomsday-style-7715286_640.jpg",
        lorem: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed. Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed. Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati beatae enim nam delectus quos error optio totam, dolorum quas recusandae illum debitis impedit dolore. Similique beatae necessitatibus eos at sed."

    }
]);
const inputRecherche = ref("");
const projetsFiltres = computed(() => {
    return projets.value.filter(projet =>
        projet.titre.toLowerCase().includes(inputRecherche.value.toLowerCase()) ||
        projet.description.toLowerCase().includes(inputRecherche.value.toLowerCase())
    );
});

const vueprojet = ref(null);

const projetCard = (id) => {
    vueprojet.value = projets.value.find(projet => projet.id === id);
    return vueprojet.value
};


</script>


<template>
    <section>
        <div>
            <div class="row">
                <div class="col-md-3"></div>
                <div class="col-md-6">
                    <div class="recherche">
                        <div class="css-nav">
                            <p>Recherche</p>
                            <input v-model="inputRecherche" class="inputRecherche form-control" type="text">
                        </div>
                    </div>
                </div>
                <div class="col-md-3"></div>
            </div>
            <div class="container-fluid">
                <div class="container">
                    <div class="row">
                        <div v-for="projet in projetsFiltres" :key="projet.id" class="col-md-6 col-lg-4 mb-4">
                            <div class="card h-100">
                                <div class="card-body">
                                    <div :id="projet.titre" class="projet">
                                        <div class="container-image">
                                            <img class="projet-image" :src="projet.image" :alt="projet.titre"
                                                @click="$emit('nav', ProjectCard, projetCard(projet.id))">
                                        </div>
                                        <h6 class="card-title">{{ projet.titre }}</h6>
                                        <p class="card-text">{{ projet.description }}</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="vide"></div>
    </section>
</template>

<style scoped>
.vide {
    margin-bottom: 650px;
}

.recherche {
    text-align: center;
    margin: 50px;
    padding-bottom: 10px;
    background: rgb(51, 51, 51);
    background: linear-gradient(90deg, rgba(51, 51, 51, 1) 0%, rgba(16, 78, 80, 1) 50%, rgba(51, 51, 51, 1) 100%);
    border-radius: 12px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
}

.inputRecherche {
    margin-bottom: 10px;
}

.card {
    background: rgb(51, 51, 51);
    background: linear-gradient(90deg, rgba(51, 51, 51, 1) 0%, rgba(16, 78, 80, 1) 50%, rgba(51, 51, 51, 1) 100%);
    border-radius: 12px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
    color: white;
}

.projet {
    text-align: center;
}

.projet-image {
    max-width: 100%;
    height: auto;
    margin-bottom: 15px;
    border-radius: 12px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
    transition: transform 0.5s ease;
    width: 100%;
    height: auto;
    cursor: pointer;
}

.projet-image:hover {
    transform: scale(1.2);
}

.container-image {
    overflow: hidden;
    border-radius: 12px;
}

.card-title {
    font-weight: bold;
}

.card-text {
    margin: 0;
}
</style>

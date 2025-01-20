<script setup>
import { ref } from 'vue';
const nom = ref("");
const email = ref("")
const message = ref("");
const validation = ref("Formulaire de Contact");
const animationConst = ref(false)
const valider = () => {
    if (nom.value !== "" && email.value !== "" && message.value !== "") {
        console.log(`Nom: ${nom.value} Email: ${email.value} Message: ${message.value}`);
        nom.value = "";
        email.value = "";
        message.value = "";
        validation.value = "Merci pour le message"
        animationConst.value = true;
        setTimeout(() => {
            validation.value = "Formulaire de Contact";
            animationConst.value = false;
        }, "2000");
    }
}

</script>

<template>
    <section>
        <div class="container-fluid">
            <div class="row">
                <div class="col-md-3"></div>
                <div class="col-md-6">
                    <div class="card">
                        <div class="card-body">
                            <div class="style">
                                <h2 :class="{ animation: animationConst }">{{ validation }}</h2>
                                <form class="contact form-control" @submit.prevent>
                                    <p>Nom</p>
                                    <input class="input input-card" v-model="nom" type="text">
                                    <p>Email</p>
                                    <input class="input" v-model="email" type="email">
                                    <p>Message</p>
                                    <div class="form-floating">
                                        <textarea class="textarea " v-model="message"></textarea>
                                    </div>
                                    <div class="div">
                                        <button @click="valider">Envoyer</button>
                                    </div>
                                </form>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-md-3"></div>
            </div>
        </div>
        <div class="vide"></div>
    </section>
</template>

<style scoped>
.vide {
    margin-bottom: 200px;
}
.container-fluid {
    margin-top: 50px;
}
.card {
    background: rgb(51, 51, 51);
    background: linear-gradient(90deg, rgba(51, 51, 51, 1) 0%, rgba(16, 78, 80, 1) 50%, rgba(51, 51, 51, 1) 100%);
    border-radius: 12px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
    color: aliceblue;
}

.input,
.textarea {
    color: aliceblue;
    background-color: transparent;
    border: 2px solid aliceblue;
    padding: 4px;
    margin-top: 5px;
    width: 200px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
}

p {
    padding-top: 10px;
}

.contact {
    text-align: center;
    background: none;
    border: none;
    color: aliceblue;
}



button {
    background: none;
    border: solid aliceblue 2px;
    border-radius: 7px;
    color: inherit;
    font: inherit;
    cursor: pointer;
    margin-top: 5px;
}

button:hover {
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
}

.animation {
    animation: clignoter 0.5s infinite alternate;
}

@keyframes clignoter {
    0% {
        color: black;
    }

    100% {
        color: white;
    }
}


p {
    padding-top: 15px;
}

@media (min-width: 1200px) {
    textarea {
        min-width: 300px;
        min-height: 150px;
    }
}
</style>

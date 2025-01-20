<script setup>
import ContactForm from '../components/ContactForm.vue';
</script>


<template>
    <footer class="footer">
        <div class="icone">
            <button @click="$emit('nav', ContactForm)"><i class="fa-solid fa-envelope"></i></button>
            <i class="fa-brands fa-facebook"></i>
            <i class="fa-brands fa-twitter"></i>
            <i class="fa-brands fa-instagram"></i>
            <i class="fa-brands fa-github"></i>
            <i class="fa-brands fa-linkedin"></i>
        </div>
        <div class="text">
            <p>&copy; 2023 Maxime</p>
        </div>
    </footer>
</template>


<style scoped>
.footer {
    background: rgb(51, 51, 51);
    background: linear-gradient(90deg, rgba(51, 51, 51, 1) 0%, rgba(16, 78, 80, 1) 50%, rgba(51, 51, 51, 1) 100%);
    border-radius: 12px;
    padding: 15px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
    position: relative;
    margin-top: 50px;
}

.text {
    text-align: center;
}

.fa-brands {
    color: aliceblue;
    background-color: black;
    margin-right: 10px;
    font-size: 20px;
    border-radius: 50px;
    padding: 5px
}

.fa-brands:hover {
    color: black;
    background-color: aliceblue;
}

.icone {
    text-align: start;
    cursor: pointer;
}

button {
    background: black;
    color: aliceblue;
    border: solid black 1px;
    font: inherit;
    cursor: pointer;
    margin-right: 10px;
    border-radius: 50px;
    padding-right: 10px;
    padding-left: 10px;
}

button:hover {
    color: black;
    background-color: aliceblue;
    border: solid aliceblue 1px;
}
</style>
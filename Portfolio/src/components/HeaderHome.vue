<script setup>
// Fait remonter la page a 0px du top du a un probleme.
const scrollToTop = () => {
    window.scrollTo({ top: 0, behavior: 'smooth' });
    setTimeout(() => {
        window.location.href = '#home';
    }, 10)
};
// De même, assurez-vous d'être en plein écran lors du défilement
const scrollToMidle = () => {
    window.scrollTo({ top: 950, behavior: 'smooth' });
    setTimeout(() => {
        window.location.href = '#project'
    }, 10)
};
</script>

<template>
    <header>
        <a href="/">
            <img src="../assets/test.png" alt="Image xmr" width="200">
        </a>
        <h1>Angel Kahlaoui</h1>
        <menu class="menu-link">
            <li><a href="#home" @click.prevent="scrollToTop">Accueil</a></li>
            <li><a href="#project" @click.prevent="scrollToMidle">Mes projets</a></li>
            <li><a href="#contact">Me contacter</a></li>
        </menu>
    </header>
</template>

<style scoped>
header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    width: auto;
    color: rgb(255, 255, 255);
    background-color: #221F31;
    padding: 20px 30px;
}

a {
    text-decoration: none;
}

.active {
    text-decoration: underline;
}

img {
    height: 50px;
}

h1 {
    flex-grow: 1;
    text-align: center;
    margin: 0;
}

menu {
    display: flex;
    gap: 20px;
}

.menu-link {
    list-style: none;
}

a {
    color: rgb(255, 255, 255);
    transition: color 0.5s;
}

a:hover {
    color: #8e38ff;
}
</style>
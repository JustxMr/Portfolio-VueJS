<script setup>
import { ref } from 'vue';
import Modal from '@/components/Modal.vue';
import emailjs from 'emailjs-com';

// Par défaut les Modals ne sont pas apparente
const showFirstModal = ref(false);
const showSecondModal = ref(false);

showFirstModal.value = false; // Première Modal
showSecondModal.value = false; // Seconde Modal

// Declaration des ref
const name = ref('');
const email = ref('');
const message = ref('');

// Fonction pour envoyer l'email
const sendEmail = () => {
const templateParams = {
  name: name.value,
  email: email.value,
  message: message.value,
};

emailjs.send(
  import.meta.env.VITE_APP_EMAILJS_SERVICE_ID,
  import.meta.env.VITE_APP_EMAILJS_TEMPLATE_ID,
  templateParams,
  import.meta.env.VITE_APP_EMAILJS_USER_ID
)
  .then((response) => {
    console.log('Message envoyé avec succès !', response.status, response.text);
    alert("Message envoyé avec succès ! ")
    // Réinitialiser le formulaire après l'envoi
    name.value = '';
    email.value = '';
    message.value = '';
  })
  .catch((error) => {
    console.error('Erreur lors de l\'envoi du message:', error);
    alert("Une erreur inattendu c'est produit !")
  });
};

</script>

<template>

  <main id="main">
    <div id="home">
      <h2 class="title">Je m'appelle Angel Kahlaoui.</h2>
      <p>
        Depuis toujours passionné par le développement web, j'ai souhaité m'instruire et poursuivre dans ce domaine. Cependant venant d'une région où l'école ne proposait pas d'études dans ce secteur, j'ai retardé mon apprentissage. Ce n'est qu'à l'âge de 21 ans que j'ai décidé de prendre les devants en m'inscrivant à une formation pour devenir développeur web et mobile.
      </p>

      <p>
        Bien qu'il existe plusieurs formations en ligne sur YouTube et d'autres plateformes, je n'avais pas d'accompagnement personnel. Cela signifiait que lorsque j'avais une question, je trouvais rarement de réponse, jusqu'à ce que je découvre le CEF (Centre Européen de Formation).
      </p>

      <p>
        Depuis que je suis cette formation, je suis en apprentissage constant et j'apprends de jour en jour. J'aime énormément la théorie mais j'apprécie encore plus la pratique.
      </p>

      <p>
        Aujourd'hui je suis fier d'avoir parcouru ce domaine et je continuerai à en apprendre davantage.
      </p>

      <p>
        Ayant un goût prononcé pour les règles et recommandations dans le développement web, telles que les conventions à respecter et les directives du W3C, je ne cesse de me perfectionner dans mon domaine.
      </p>
    </div>

    <div id="project">
      <h2 class="second_title">Mes projets réalisé.</h2>
      <section class="modal_contenair">
        <h3>Dynamiser un espace commentaire</h3>
        <button @click="showFirstModal = true">
          <img src="../assets/dynami.png" alt="dynamiser un espace commentaire">
        </button>
        <Modal class="first_modal" :is-Visible="showFirstModal" @close="showFirstModal = false">
          <div class="modal_content">
            <h3 class="modal_title">Dynamiser un espace commentaire</h3>
            <img src="../assets/dynami.png" alt="dynamiser un espace commentaire a l'aide de javascript">
            <p><strong>Langage de programation utilisé => HTML , CSS & JavaScript</strong></p>
            <p class="p_modal">Date de création : </p>
            <time datetime="2025-02-24"> 24/02/2025</time>
            <a href="https://github.com/JustxMr/DYNAMISER-UN-ESPACE-COMMENTAIRE" target="_blank" rel="lien dynamiser un espace comm">Accèder a ma réalisation</a>
          </div>
        </Modal>
      </section>

      <section class="modal_contenair">
        <h3>Crée un CV en HTML & CSS</h3>
        <button @click="showSecondModal = true">
          <img src="../assets/cv.png" alt="CV HTML & CSS">
        </button>
        <Modal class="second_modal" :is-Visible="showSecondModal" @close="showSecondModal = false">
          <div class="modal_content">
            <h3 class="modal_title">Créer un CV en HTML & CSS</h3>
            <img src="../assets/cv.png" alt="CV en HTML & CSS">
            <p><strong>Langage de programation utilisé => HTML & CSS</strong></p>
            <p class="p_modal">Date de création : </p>
            <time datetime="2024-07-30"> 30/07/2024</time>
            <a href="https://github.com/JustxMr/CV" target="_blank" rel="lien cv">Accèder a ma réalisation</a>
          </div>
        </Modal>
      </section>
    </div>

    <div id="contact">
      <h3 class="formTitle">Formulaire de contact</h3>
      <form @submit.prevent="sendEmail">

        <label for="name">Nom & prénom</label>
        <input v-model="name" type="text" name="name" id="name" required minlength="3" maxlength="20" placeholder="John Doe">

        <label for="email">Email</label>
        <input v-model="email" type="email" name="email" id="email" pattern=".+@gmail.com" required placeholder="example@exemple.com">

        <label for="message">Message</label>
        <textarea v-model="message" name="message" id="message"></textarea>

        <button class="submitForm" type="submit">Envoyez</button>

      </form>
    </div>
  </main>

</template>

<style scoped>
#home {
  width: 30%;
  height: 50%;
  margin: 94px auto;
  border: 1px solid rgb(255, 255, 255);
  border-radius: 150px;
  box-shadow: 20px 20px 11px -2px #221F31;
  color: white;
}

#project {
  width: 37.5%;
  margin: 2rem auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: #fff;
}

#contact {
  padding: 30px;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  width: 350px;
  text-align: center;
  color: #fff;
  margin: 100px auto; /* Centre horizontalement */
}

label {
  margin-top: 10px;
  font-weight: bold;
  display: block;
  text-align: left;
  color: #fff;
}

input, textarea {
  width: 100%;
  padding: 10px;
  margin-top: 5px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  resize: none;
  background: rgb(218, 201, 201);
  color: black;
}

textarea {
  height: 150px;
}

.submitForm {
  margin-top: 15px;
  padding: 10px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  width: 100%;
}

.submitForm:hover {
  background-color: #0056b3;
}

.mail {
  color: #fff;
  text-decoration: none;
}

.title {
  width: 60%;
  margin: 45px auto;
}

#home p {
  width: 55%;
  margin: 50px auto;
}

.modal_content p {
  display: flex;
  justify-content: center;
  margin-top: 10px;
}

.modal_content time {
  display: flex;
  justify-content: center;
}

div > a {
  position: relative;
  top: 20px;
  color: rgb(255, 255, 255);
  font-size: large;
  margin-top: 10px;
  padding: 5px;
  text-decoration: none;
  border: 1px solid #fff;
  border-radius: 10px;
}

div > a:hover {
  box-shadow: 5px 5px 10px -1px rgba(0, 0, 0, 0.4);
}

button {
  display: block;
  width: fit-content;
  margin: auto;
  color: #010440
}

.second_title {
  width: fit-content;
  margin: 20px auto 20px;
}

section > h3 {
  width: fit-content;
  margin: auto;
  margin-top: 3.5rem;
  margin-bottom: .4rem;
  font-size: 1.1rem;
}

img {
  display: block;
  width: 350px;
  height: 200px;
  margin: auto;
}

.modal_contenair {
  margin-bottom: 1em;
}


.modal_content {
  height: 100%;
  color: #fff;
}

.modal_contenair:hover {
  outline: 1px solid #fff; /* Préférence pour outline / permet de pas faire de décalage / n'ajoute pas du coutenu mais le superpose */
  border-radius: 0.1em;
  box-shadow: 20px 20px 11px -2px #221F31;
}

.modal_title {
  margin: 10px;
  font-size: 25px;
  color: #fff;
}
</style>
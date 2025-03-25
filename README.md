# Portfolio

Ce modèle devrait vous aider à démarrer le développement avec Vue 3 et Vite.

## Configuration IDE Recommandée

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (et désactiver Vetur).

## Personnaliser la Configuration

Consultez la [Référence de Configuration de Vite](https://vite.dev/config/).

# Prérequis : Installer la dernière version de `Node JS` et redemarrer votre machine ci besoins.

[NodeJS](https://nodejs.org/fr/download).

## Vous devriez effectuer cette commande pour installer tout ce qui est nécessaire au bon fonctionnement de l'application 

```sh
npm install
```

### Compilation et rechargement à chaud pour le développement / vous permet de voir en temps réel votre projet web

```sh
npm run dev
```

### Compilation et minification pour la production / Permet de crée un nouveau fichier converti pour être heberger

```sh
npm run build
```
# Pour installer `EmailJS` veuillez suivre les indications ci-dessous.

Crée un fichier `.env` a la racine du projet et entrer ces information:

VITE_APP_EMAILJS_USER_ID=YOUR_USER_ID
VITE_APP_EMAILJS_SERVICE_ID=YOUR_SERVICE_ID
VITE_APP_EMAILJS_TEMPLATE_ID=YOUR_TEMPLATE_ID

Assurer vous d'avoir créer un compte chez `Emailjs`

Enfin installer la bibliothéque qui vous permettra que tout cela fonctionne correctement:

```sh
npm install emailjs-com
```
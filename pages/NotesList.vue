<template>
    <div class="notes-list-page">
      <h1>Liste des notes</h1>
      <ul>
        <li v-for="(note, index) in notes" :key="index">
          <h2>{{ note.title }}</h2>
          <p>{{ note.content }}</p>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        notes: [
          { title: 'Cours sur Nuxt', content: 'Contenu de la note 1' },
          { title: 'Cours sur Laravel', content: 'Contenu de la note 2' },
          { title: 'Cours sur le modele MVC', content: 'Contenu de la note 3' }
          
        ]
      }
    }
  }
  </script>
  
  <style scoped>

  .notes-list-page {
    height: 100vh;
    margin-left: 250px;
    padding: 20px;
    background-image: url(../static/cozy.gif);
    background-size: cover;
    color: white;
    background-position: right;
    overflow-y: auto; /* pour le defilement*/
  }
  .notes-list-page h1 {
    margin-bottom: 20px;
    margin-top: 50px;
    font-weight: 700;
    
  }
  .notes-list-page ul {
    list-style: none;
    padding: 0;
  }
  .notes-list-page li {
    border: 1px solid #e1898e;
    border-radius: 10px;
    box-shadow: 5px 10px 15px #e1898e;
    backdrop-filter: blur(1px);
    padding: 10px;
    margin-bottom: 10px;
    cursor: pointer;

  }
  .notes-list-page h2 {
    margin-bottom: 5px;
    font-weight: 500;

  }
  </style>
  
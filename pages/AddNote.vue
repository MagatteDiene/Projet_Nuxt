<template>
    <div class="add-note-page">
      <h1>Ajouter une <span>ℕ𝕠𝕥𝕖</span></h1>
      <form @submit.prevent="submitNote">
        <div>
          <label for="title">Titre :</label>
          <input type="text" id="title" v-model="note.title" required>
        </div>
        <div>
          <label for="content">Contenu :</label>
          <textarea id="content" v-model="note.content" required></textarea>
        </div>
        <button type="submit">Ajouter la note</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        note: {
          title: '',
          content: ''
        }
      }
    },
    methods: {
      submitNote() {
        // Logique pour soumettre la note (à implémenter)
        console.log('Note soumise :', this.note);
        // Rediriger l'utilisateur vers une autre page (par exemple, la liste des notes)
        this.$router.push('/NotesList');
      }
    }
  }
  </script>
  
  <style scoped>
  /* Styles spécifiques à la page d'ajout de note */
  .add-note-page {
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items:end;
    background-image: url(../static/mitsuki2.png);
    background-size: cover;
  }
  .add-note-page h1{
    margin-right: 210px;
  }
  .add-note-page h1 span {
  color: #e1898e; 
}
  .add-note-page form {
    width: 300px;
    padding: 20px;
    border: 1px solid #e1898e;
    box-shadow: 5px 10px 15px #e1898e;
    backdrop-filter: blur(1px);
    border-radius: 10px;
    margin-right: 200px;
  }
  .add-note-page form label {
    display: block;
    margin-bottom: 10px;
    font-weight: 600;

  }
  .add-note-page form input,
  .add-note-page form textarea {
    width: 100%;
    padding: 8px;
    margin-bottom: 15px;
    border: 1px solid #e1898e;
    background: white;
    border-radius: 5px;
    outline: none;
  }
  .add-note-page form button {
    width: 100%;
    padding: 10px;
    background-color: #e1898e;
    color: #fff;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    font-weight: 600;

  }
  .add-note-page form button:hover {
    background-color: white;
    color: #e1898e;
    transition: .5s;
  }
  </style>
  
<template>
  <div>
    <Sidebar/>
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
      // Sauvegarder la note dans le stockage local
      this.saveNoteToLocal(this.note);
      // Rediriger l'utilisateur vers une autre page (par exemple, la liste des notes)
      this.$router.push('/NotesList');
    },
    saveNoteToLocal(note) {
      // Récupérer les notes existantes dans le stockage local (s'il y en a)
      const existingNotes = JSON.parse(localStorage.getItem('notes')) || [];
      // Ajouter la nouvelle note à la liste des notes existantes
      existingNotes.push(note);
      // Mettre à jour les données dans le stockage local
      localStorage.setItem('notes', JSON.stringify(existingNotes));
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
  
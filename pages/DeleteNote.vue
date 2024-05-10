<template>
  <div>
    <Sidebar/>
    <div class="delete-note-page">
      <h1>Supprimer une <span>ℕ𝕠𝕥𝕖</span></h1>
      <ul>
        <li v-for="(note, index) in notes" :key="index">
          <div>
            <h2>{{ note.title }}</h2>
            <button @click="deleteNote(index)">Supprimer</button>
          </div>
        </li>
      </ul>
    </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        notes: []
      };
    },
    mounted() {
      this.loadNotes();
    },
    methods: {
      async loadNotes() {
        const savedNotes = JSON.parse(localStorage.getItem('notes')) || [];
        this.notes = savedNotes;
      },
      deleteNote(index) {
        this.notes.splice(index, 1);
        localStorage.setItem('notes', JSON.stringify(this.notes));
      }
    }
  };
  </script>
  
  <style scoped>
  .delete-note-page {
    height: 100vh;
    margin-left: 250px;
    padding: 20px;
    background-image: url(../static/Cool.gif);
    background-size: cover;
    color: white;
    background-position: right;
    overflow-y: auto; /* pour le défilement */
  }
  .delete-note-page h1 span{
    color: #e1898e;
  }
  .delete-note-page h1 {
    margin-bottom: 20px;
    margin-top: 50px;
    font-weight: 700;
  }
  .delete-note-page ul {
    list-style: none;
    padding: 0;
  }
  .delete-note-page li {
    border: 1px solid #e1898e;
    border-radius: 10px;
    box-shadow: 5px 10px 15px #e1898e;
    backdrop-filter: blur(1px);
    padding: 10px;
    margin-bottom: 10px;
  }
  .delete-note-page h2 {
    margin-bottom: 5px;
    font-weight: 500;
  }
  .delete-note-page button {
    background-color: #e1898e;
    color: white;
    border: none;
    padding: 5px 10px;
    border-radius: 5px;
    cursor: pointer;
  }
  .delete-note-page button:hover {
    background-color: white;
    color: #e1898e;
    transition: .5s;
  }
  </style>
  
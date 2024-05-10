<template>
    <div class="search-note-page">
      <h1>Rechercher une <span>ℕ𝕠𝕥𝕖</span></h1>
      <input type="text" v-model="searchQuery" placeholder="Rechercher...">
      <ul>
        <li v-for="(note, index) in filteredNotes" :key="index" @click="redirectToNotesList(note)">
          <h2>{{ note.title }}</h2>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        searchQuery: '',
        notes: []
      };
    },
    mounted() {
      this.loadNotes();
    },
    computed: {
      filteredNotes() {
        const query = this.searchQuery.toLowerCase();
        return this.notes.filter(note => 
          note.title.toLowerCase().includes(query) 
        );
      }
    },
    methods: {
      loadNotes() {
        this.notes = JSON.parse(localStorage.getItem('notes')) || [];
      },
      redirectToNotesList(note) {
        // Supposez que vous avez une route nommée 'notes-list'
        this.$router.push('/NotesList');
      }
    }
  };
  </script>
  
  <style scoped>
  .search-note-page {
    height: 100vh;
    margin-left: 250px;
    padding: 20px;
    background-image: url(../static/img2.png);
    background-size: cover;
    color: white;
    background-position: right;
    overflow-y: auto; /* pour le défilement */
  }
  .search-note-page h1 {
    margin-bottom: 20px;
    margin-top: 50px;
    font-weight: 700;
  }
  .search-note-page h1 span{
    color: black;
  }
  .search-note-page input{
    width: 100%;
    padding: 8px;
    margin-bottom: 15px;
    border: 2px solid #e1898e;
    background: white;
    border-radius: 5px;
    outline: none;
  }
  .search-note-page ul {
    list-style: none;
    padding: 0;
  }
  .search-note-page li {
    border: 1px solid #e1898e;
    border-radius: 10px;
    box-shadow: 5px 10px 15px #e1898e;
    backdrop-filter: blur(1px);
    padding: 10px;
    margin-bottom: 10px;
    cursor: pointer;
  }
  .search-note-page h2 {
    margin-bottom: 5px;
    font-weight: 500;
  }
  </style>
  
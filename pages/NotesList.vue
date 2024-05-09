<template>
  <div class="notes-list-page">
    <h1>Liste des notes</h1>
    <ul>
      <li v-for="(note, index) in notes" :key="index">
        <h2 @click="toggleNoteContent(index)">{{ note.title }}</h2>
        <p v-if="note.showFullContent" class="note-content">{{ note.content }}</p>
      </li>
    </ul>
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
    const savedNotes = JSON.parse(localStorage.getItem('notes')) || [];
    this.notes = savedNotes.map(note => ({ ...note, showFullContent: false }));
  },
  methods: {
    toggleNoteContent(index) {
      this.$set(this.notes[index], 'showFullContent', !this.notes[index].showFullContent);
    }
  }
};
</script>

<style scoped>
.notes-list-page li {
  cursor: pointer;
}
.notes-list-page {
  height: 100vh;
  margin-left: 250px;
  padding: 20px;
  background-image: url(../static/cozy.gif);
  background-size: cover;
  color: white;
  background-position: right;
  overflow-y: auto; /* pour le défilement */
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
}
.notes-list-page h2 {
  margin-bottom: 5px;
  font-weight: 500;
}
.note-content {
  word-wrap: break-word; /* ou overflow-wrap: break-word; */
}
</style>

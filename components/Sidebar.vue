<template>
<div class="body">
    <nav id="sidebar" class="col-md-3 col-lg-2 d-md-block bg-light sidebar">
      <div class="position-sticky d-flex flex-column vh-100">
        <img src="../static/notekeeper.png" alt="" >
        <ul class="nav flex-column">
          <li class="nav-item">
            <nuxt-link class="nav-link-home" to="/">Accueil</nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/NotesList"><i class='bx bx-list-ul'></i> Liste des notes </nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/AddNote"><i class='bx bx-book-add'></i> Ajouter une note </nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/DeleteNote"><i class='bx bx-eraser'></i> Supprimer une note </nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/SearchNote"><i class='bx bx-search-alt'></i> Rechercher une note </nuxt-link>
          </li>
        </ul>
        
      </div>
      
    </nav>
    </div>

  </template>
  
  <script>
  export default {
    name: 'Sidebar'
  }
  </script>
  
  <style scoped>
  /* Styles spécifiques à la sidebar */
  #sidebar {
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  width: 250px;
    
  }
  
  /* Styles généraux */
  
  .nav-link{
    color: #e1898e;
  }
  .nav-link:hover{
    color: white;
    
  }

  *{
    background-color: black;
  }

  .nav-link-home{
    color: white;
    font-weight: bolder;
    background-color: #e1898e;
    border-radius: 3px;
    text-decoration: none;
    padding: 10px 96px 20px;
  }
  .nav-link-home:hover{
    color:#e1898e;
    background-color: white;
    transition: .5s;
  }
  </style>
  
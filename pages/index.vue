<template>
  <div class="home">
    <h1>Bienvenue sur <span>ℕ𝕠𝕥𝕖𝕂𝕖𝕖𝕡𝕖𝕣 </span><i class='bx bx-edit-alt'></i></h1>
    <p>L'application specialement conçue pour <br> vous aider à gérer vos notes.</p>
    <!-- Ajoutez plus de contenu ici si nécessaire -->
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>

<style scoped>
  .home{
   height: 100vh;
  display: flex; 
  flex-direction: column; 
  justify-content: center; 
  align-items:end; 
  background-image: url('../static/mitsuki.png'); 
  background-size: cover; 
  }
  .home h1{
    margin-right: 150px;
    margin-bottom: 30px;
    margin-top: 160px;
    font-weight: 700;
  }
  .home h1 span {
  color: #e1898e; 

}
.home p {
  color: #e1898e; 
  margin-right: 30px;
  margin-top: 140px;
  font-weight: 700;


}

</style>
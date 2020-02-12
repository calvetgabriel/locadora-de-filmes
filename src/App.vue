<template>
  <div id="app">
    <b-container>
    <h1>{{ title }}</h1>
    <!-- <h2>{{ horas }}</h2> -->
    <!-- Comentario maneiro do amiginho -->
    <p>Comentario maneiro do amiginho</p>

    <h3 v-if ="horas >= 9 && horas < 17" id="aberta">ABERTA</h3>
    <h3 v-else-if="horas >= 17 && horas < 18" id="proxima-fechar">PRÓXIMA A FECHAR</h3>
    <h3 v-else id="fechada">FECHADA</h3>

    <div class="row">
      <div class="col">
        <h2>Filmes Encontrados</h2>
      </div>
    </div>

    <ul class="lista">    
      <li  v-for="filme in filmes" v-bind:key="filme">
        <div class="row">
          <div class="col">
            <div class= "card">
              <img :src="filme.imagem" class="card-img-top">
              <h5 class="card-title">{{filme.titulo}}</h5>
              <p class="card-text">{{filme.descricao}}</p>
              <p class="card-text">{{filme.valor}}</p>
              <a href="#" class="btn btn-primary">Alugar</a>
            </div>    
          </div> 
        </div>
      </li>
    </ul>      
    </b-container>
  </div>
</template>

<script>

  

export default {
  name: 'App',
  components: {},
  data(){
    return {
    title:'Locadora de Filmes',
    horas: new Date().getHours(),    
    filmes: [
      {id:1, titulo: "Uma Nova Esperança", descricao: "Episódio IV", valor: 20, imagem: "https://m.media-amazon.com/images/M/MV5BNzVlY2MwMjktM2E4OS00Y2Y3LWE3ZjctYzhkZGM3YzA1ZWM2XkEyXkFqcGdeQXVyNzkwMjQ5NzM@._V1_.jpg" },
      {id:2, titulo:"O Império Contra-Ataca", descricao: "Episódio V", valor: 20, imagem: "https://a-static.mlcdn.com.br/574x431/star-wars-episode-v-the-empire-strikes-back-marvel/saraiva/8982296/c0507aae93cec745ab3247d1ad62dfc4.jpg" }, 
      {id:3, titulo:"O Retorno de Jedi", descricao: "Episódio VI", valor: 20, imagem: "https://upload.wikimedia.org/wikipedia/pt/thumb/b/b2/ReturnOfTheJediPoster1983.jpg/250px-ReturnOfTheJediPoster1983.jpg" }
      ]    
    }
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#aberta {
  color: blue;
}

#proxima-fechar {
  color: orange;
}

#fechada{
  color: red;
}


</style>

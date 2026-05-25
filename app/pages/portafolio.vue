<template>
  <section class="portafolio">
    <h2>Mi Portafolio</h2>
    <p>Estos son algunos de mis proyectos.</p>

    <div class="proyectos">
      <div class="card">
        <h3>Proyecto 1</h3>
        <P>Juego de ajedrez </P>
       <a 
  href="https://github.com/Jimenazoe/AJEDREZ-ED" 
  target="_blank"
  class="github-btn"
>
  Ver en GitHub
</a>
      </div>

      <div class="card">
        <h3>Proyecto 2</h3>
        <p>Figura 3D STL</p>
          <a 
  href="https://github.com/Jimenazoe/Mulan-3D" 
  target="_blank"
  class="github-btn"
>
  Ver en GitHub
</a>
      </div>

       <div class="card">
        <h3>Proyecto 3</h3>
        <p>Pagina API</p>
                <a 
  href="https://github.com/Jimenazoe/Tienda_ropa" 
  target="_blank"
  class="github-btn"
>
  Ver en GitHub
</a>
      </div>

       <div class="card">
        <h3>Proyecto 4</h3>
        <p>Desintegrador de Particulas</p>
                <a 
  href="https://github.com/Jimenazoe/Desintegrador-de-particulas" 
  target="_blank"
  class="github-btn"
>
  Ver en GitHub
</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.portafolio {
  padding: 80px 20px;
  color: white;
  text-align: center;
}

.proyectos {
  display: flex;
  gap: 20px;
  justify-content: center;
  flex-wrap: wrap;
  margin-top: 30px;
}

.card {
  background: #111;
  padding: 20px;
  border-radius: 15px;
  width: 250px;
}
</style>
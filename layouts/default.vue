<template>
  <div>
    <div class="header">
      <div class="contenedor">
        <img src="/img/ico-logo.png" style="width: 3em; min-width: 3em;">
        <br>
        <span class="text-white font-weight-bold">Frontend Test</span>
      </div>      
    </div>
    <Nuxt />
  </div>
</template>

<style>
body{
  background: -webkit-linear-gradient(top, rgba(0,250,104,1) 0%, rgba(0,247,255,1) 100%);
  background-repeat: no-repeat;
  background-attachment: fixed
}
.header{
  display: flex;
  align-items: center;
  justify-content: center;
}

.contenedor{
        display: flex;
        flex-direction: column;
        align-items: center;
        align-content: center;
        margin: 2em;
        padding: 1em;
    }
</style>

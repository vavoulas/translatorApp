<template>
  <div id="translateOutput" class="card text-white bg-dark mb-3">
    <div class="card-body">
      <h1 class="card-title">{{translatedText}}</h1>
    </div>
   
  </div>
</template>

<script>


export default {
  name: 'translateOuput',
  props:['translatedText']
  
  
  
}   
</script>

<style>
  #translateOutput{
    text-align: center;
    font-size: 1.8em;
    border-radius: 5%;

  }
</style>

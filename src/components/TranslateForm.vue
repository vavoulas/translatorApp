<template>
  <div  id="translateForm">
    <form v-on:submit="formSubmit" class="form-group">
      <input type="text" class="form-control" v-model="textToTranslate" placeholder="Δώσε μια λέξη....">
      <select v-model="language" class="form-control" id="sel">
        <option value="el">Ελληνικά</option>
        <option value="en">Αγγλικά</option>
        <option value="de">Γερμανικά</option>
        <option value="ru">Ρώσικα</option>
        <option value="it">Ιταλικά</option>
        <option value="es">Ισπανικά</option>
        <option value="fr">Γαλλικά</option>
        <option value="pt">Πορτογαλικά</option>
        <option value="tr">Τουρκικά</option>
        <option value="sv">Σουηδικά</option>
      </select>
      <br>
      <input type="submit" class="btn btn-success center-block" value="Μετέφρασε">
    </form>
  </div>
</template>

<script>


export default {
  name: 'translateForm',
  data(){
    return {
      textToTranslate:"",
      language:''
    }
  },
  created(){
    this.language = 'el';
  },
  methods:{
    formSubmit(e){
      this.$emit('formSubmit', this.textToTranslate, this.language);
      e.preventDefault();


    }
  }
  
}   
</script>

<style>
  #translateForm{
    border-radius: 10px;
    text-align: center;
    
  }
</style>

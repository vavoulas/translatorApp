<template>
  <div id="app">
    <h1 class="text-center">Απλός Μεταφραστής</h1>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
    <TranslateOuput v-text="translatedText"></TranslateOuput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOuput from './components/TranslateOutput'

export default {
  name: 'app',
  components: {
    TranslateForm,
    TranslateOuput
    
  },
  data : function(){
      return {
        translatedText:''
      }
  },
  methods: {
    translateText:function(text, language){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180616T215339Z.4bd7ec15ec677379.e47029d11726bf539b8aeee42bc16ee8ca5fcfac&lang='+language+'&text='+text)
      .then((response)=>{
        this.translatedText=response.body.text[0];
      })
    }
  }
}   
</script>

<style>

#app {
  
  
  margin: 0 auto;
  
  color: #3c0e87;
  margin-top: 80px;
  max-width:300px;
}
</style>

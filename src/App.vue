<template>
  <div class="text-center" id="app">
    <h1>Word Translate</h1>
    <h5>Powered By <span style="color:green"><a href="https://vuejs.org/">Vue.JS</a></span></h5>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
    <TranslateOutput v-text="translatedText"></TranslateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'

export default {
  name: 'app',
  components: {
    TranslateForm,
    TranslateOutput
  },
  data: function(){
    return {
      translatedText: ''
    }
  },
  methods: {
    translateText: function(text, language) {
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170906T180110Z.f13837ac92b42a4f.7fcbabbe589070799c4c4dd716388f1457a89374&lang='+language+'&text='+text)
      .then((respone) => {

        this.translatedText = (respone.body.text[0])
      });
    }
  }
}
</script>

<style>
  body {
    background:#fefefe;
  }
  #image{
    width:25%;
  }
</style>

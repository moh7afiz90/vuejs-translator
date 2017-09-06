<template>
  <div id="app">
    <h1>Word Translate</h1>
    <h5>Powered By Vue.js</h5>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'

export default {
  name: 'app',
  components: {
    TranslateForm
  },
  methods: {
    translateText: function(text) {
      this.$http.get(https://translate.yandex.net/api/v1.5/tr.json/translate ?
key='trnsl.1.1.20170906T180110Z.f13837ac92b42a4f.7fcbabbe589070799c4c4dd716388f1457a89374&lang=ar&text='+text);
    }
  }
}
</script>

<style>
#app {

}
</style>

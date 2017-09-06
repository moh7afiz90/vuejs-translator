<template>
  <div id="translateFrom">
    <form v-on:submit="formSubmit">
      <input type="text" v-model="textToTranslate" placeholder="Enter a word....">
      <input type="submit" name="" value="Translate">
    </form>
  </div>
</template>

<script>


export default {
  name: 'translateForm',
  data() {
    return {
      textToTranslate: ''
    }
  },
  methods: {
    formSubmit(e){
      this.$emit('formSubmit', this.textToTranslate);
      e.preventDefault();
    }
  }
}
</script>

<style>

</style>

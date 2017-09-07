<template>
  <div class="row" id="translateFrom">
    <div class="col-md-6 col-md-offset-3">
      <form id="tranform" class="well form-inline" v-on:submit="formSubmit">
        <input class="form-control" type="text" v-model="textToTranslate" placeholder="Enter a word....">
        <select class="form-control" v-model="language">
          <option value="az">Azerbaijan</option>
          <option value="sq">Albanian</option>
          <option value="am">Amharic</option>
          <option value="ar">Arabic</option>
          <option value="hy">Armenian</option>
          <option value="af">Afrikaan</option>
          <option value="tt">Tatar</option>
          <option value="te">Telugu</option>
          <option value="tr">Turkish</option>
          <option value="udm">Udmurt</option>
          <option value="uz">Uzbek</option>
          <option value="uk">Ukrainian</option>
          <option value="ur">Urdu</option>
          <option value="fi">Finnish</option>
          <option value="fr">French</option>
          <option value="es">Hindi</option>
          <option value="ms">Croatian</option>
          <option value="cs">Czech</option>
          <option value="sv">Swedish</option>
          <option value="gd">Scottish</option>
          <option value="et">Estonian</option>
          <option value="eo">Esperanto</option>
          <option value="jv">Javanese</option>
          <option value="ja">Japanese</option>
        </select>
        <input class="btn btn-primary" type="submit" name="" value="Translate">
      </form>
    </div>
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
  created() {
    this.language = 'ar';
  },
  methods: {
    formSubmit(e){
      this.$emit('formSubmit', this.textToTranslate, this.language);
      e.preventDefault();
    }
  }
}
</script>

<style>
  #tranform{
    border-radius:10px;
    border: 1px #ccc solid;
  }
</style>

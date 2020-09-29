<template>
  <div id="app">
    <div class="corpo">

      <h1 class="mb-4">Cadastro de IMC</h1>

      <div class="row">

        <div class="col-2">
          <div class="form-group">
            <label for="peso">Peso(kg)</label>
            <input type="text" class="form-control" v-model="peso" placeholder="Digite seu peso" @keypress="calcularImc">
          </div>
        </div>

        <div class="col-2">
          <div class="form-group">
            <label for="altura">Altura(ex: 1.67)</label>
            <input type="text" class="form-control" v-model="altura" placeholder="Digite sua altura" v-on:keypress="calcularImc">
          </div>
        </div>

        <div class="col-3">
          <p>Seu IMC é: {{ imc }}</p>
        </div>

      </div>
      
    </div>

  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      peso: '',
      altura: '',
      imc: ''
    }
  },

  methods: {
    calcularImc: function() {
      if (this.peso > 0 && this.altura > 1.00) {
        this.imc = (this.peso / (this.altura * this.altura)).toFixed(2);
      }
    }
  },
}
</script>

<style>
.corpo{
    padding: 20px;
}

p{
    margin-top: 2rem;
}
</style>

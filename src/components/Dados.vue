<template>
  <div class="text-center">
    <button class="btn btn-success btn-lg" v-on:click="tirarDados()">
      Tirar
    </button>
    <br />
    <img v-bind:src="dadoIzquierdo" alt="Dado izquierdo" />
    <img v-bind:src="dadoDerecho" alt="Dado derecho" />
    <h1 id="ganador">
    </h1>
  </div>
</template>

<script defer>
export default {
  data() {
    return {
      dadoIzquierdo: "assets/img/dice1.png",
      dadoDerecho: "assets/img/dice2.png",
      numero1: 1,
      numero2: 2
    };
  },

  methods: {
    tirarDados() {
      this.numero1 = Math.floor(Math.random() * 6) + 1;
      this.numero2 = Math.floor(Math.random() * 6) + 1;
      this.dadoIzquierdo = "assets/img/dice" + this.numero1 + ".png";
      this.dadoDerecho = "assets/img/dice" + this.numero2 + ".png";

      let result = document.getElementById('ganador');

      if (this.numero1 === this.numero2) {
        result.innerHTML = '<span class="badge badge-success">¡¡Ganaste!!</span>';
      }else {
        result.innerHTML = '';
      }
    },
  },
};
</script>

<style scoped>
.text-center {
  padding-top: 100px;
  background-color: #e9ecef;
  height: 100vh;
}
img {
  height: 300px;
  width: 300px;
  background-color: red;
  margin: 20px;
  border-radius: 20px;
}
</style>
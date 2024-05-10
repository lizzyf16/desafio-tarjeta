<template>
  <div class="contenedorTarjeta">
    <form>
      <div>
        <label>Título de la tarjeta: </label>
        <input v-model="tituloTarjeta" />
      </div>
      <!-- <div>
          <label>Chip SRC: </label>
          <input  />
        </div> -->
      <div>
        <label>Número: </label>
        <input v-model="tarjetaNumero" />
      </div>
      <div>
        <label>Fecha de expiración: </label>
        <input v-model="fechaExpiracion" />
      </div>
      <div>
        <label>Propietario: </label>
        <input v-model="propietario" />
      </div>
      <div>
        <label for="tipo">Tipo de tarjeta SRC: </label>
        <select name="tipo" id="tipo" v-model="tarjetaRegistro.tipo">
          <!-- se repite n cantidad de veces -->
          <option v-for="tipo in tipos" :key="tipo.id" :value="tipo.path">{{ tipo.texto }}</option>
        </select>
      </div>
    </form>
    <div class="tarjeta">
      <h3>{{ tituloTarjeta }}</h3>
      <img width="40px" src="/chip.png" alt="chip" />
      <div>
        <h2>{{ tarjetaNumero }}</h2>
        <span>Fecha Exp: <b>{{ fechaExpiracion }}</b></span>
      </div>
      <footer >
        <span>{{ propietario }}</span>
        <img  :src="tarjetaRegistro.tipo" height="60"/>
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CardTarjeta',

  data() {
    return {
      tituloTarjeta: "Aquí se agrega el titulo",
        tarjetaNumero: "400 500 600 700",
        fechaExpiracion: "01/30",
        propietario: "LIZ MARY FERNANDEZ M.",
      tarjetaRegistro: {
        tipo: "",
      },
      tipos: [
        { id: 1, path: "/master1.png", texto: "Master Card" },
        { id: 2, path: "/visa.png", texto: "Visa" },
        { id: 3, path: "/american.png", texto: "American Express" },
      ],
    }
  }
  // data (){

  //   return{
  //     tituloTarjeta:"Aquí se agrega el titulo",
  //     tarjetaNumero: "400 500 600 700",
  //     fechaExpiracion:"01/30",
  //     propietario: "LIZ MARY FERNANDEZ M.",
  //     chip:"/public/chip.png",
  //     imagen:{
  //       tipo:"",
  //       nombreTipo:"Tipo de Tartjeta",
  //     },
  //     tipos: [
  //         {id: 1, path: "/assets/ime/master.png", texto: "Master Card"},
  //         {id: 2, path: "/assets/img/visa.png", texto: "Visa"},
  //     ],
  //   }
  // },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
* {
  margin: 0;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
}

h1 {
  padding-top: 40px;
  font-family: sans-serif;
}

.contenedorTarjeta {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 60vh;
  font-size: 10px;
  font-family: sans-serif;
  gap: 40px;
}

#app {
  display: flex;
  gap: 40px;
}

form {
  padding: 18px;
  border-radius: 20px;
  border: ridge 1px;
  box-shadow: 1px 1px 1px 1px gray;
  font-weight: bold;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
}

form div {
  display: grid;
  grid-template-columns: 100px 200px;
  align-items: center;
  gap: 5px;
}

form div label {
  text-align: right;
}

.tarjeta {
  width: 400px;
  height: 230px;
  background: #1c1a1e;
  color: white;
  border-radius: 20px;
  padding: 20px;
  box-shadow: 0px 0px 10px 2px black;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

h3 {
  font-size: 20px;
}

h2 {
  font-size: 30px;
  letter-spacing: 10px;
  margin-bottom: 15px;
  text-shadow: 0px 0px 1px gold;
  font-family: Times;
}

b {
  font-size: 16px;
}

footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  font-weight: bold;
  font-size: 18px;
  text-transform: uppercase;
  font-style: italic;
}
</style>

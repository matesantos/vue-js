<template>
    <div id="app">
      <h1>Projeto MontHall</h1>
      <div class="form">
            <div v-if="!started">
                <label for="portsAmount">Quantas portas? </label>
                <input type="text" id="portsAmount" size="3"
                    v-model.number="portsAmount">
            </div>
            <div v-if="!started">
                <label for="selectedPort">Qual porta é premiada? </label>
                <input type="text" id="selectedPort" size="3"
                    v-model.number="selectedPort">
            </div>
            <button v-if="!started" @click="started = true">Iniciar</button>
            <button v-if="started" @click="started = false">Reiniciar</button>
      </div>
      <div class="doors" v-if="started">
          <div v-for="p in portsAmount" :key="p">
              <Door :number='p' :hasGift="p === selectedPort"/>
          </div>
      </div>    
        </div>
</template>

<script>
import Door from "./components/door/Door";

export default {
    name: 'App',
    components: { Door },
    data: function() {
        return {
            started: false,
            portsAmount: 3,
            selectedPort: null
        }
    }
}

</script>

<style>
* {
    font-family: 'Montserrat', sans-serif;
    box-sizing: border-box;
}

body {
    color: #ffffff;
    background: linear-gradient(to right, rgb(21,153,87), rgb(21,87,157));
}

#app {
    display: flex;
    flex-direction: column;
    align-items: center;
}

#app h1 {
    border: solid 1px #0004;
    background-color: #0004;
    padding: 20px;
    margin-bottom: 60px;
}

.form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.form, .form input, .form button {
    scroll-margin-bottom: 10px;
    font-size: 2rem;
}

.doors {
    align-items: stretch;
    margin-top: 40px;
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
}
</style>
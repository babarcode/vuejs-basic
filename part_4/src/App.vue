<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    
    <div
      class="static"
      v-bind:class="{ active: isActive, 'text-danger': hasError }"
    >
      Test Binding Class
    </div>
    <p><button @click="changeClassName">Change Class</button></p>

    <div v-bind:style="{ color: activeColor, fontSize: fontSize + 'px' }">Test Binding Style</div>
    <p><button v-on:click="changeStyle">Change Style</button></p>

    <div>
      <strong>Computed Properties</strong>
      <hr>
      {{ produk }} - {{ reversedProduk }}
      <br>
      <input type="text" v-model="brand">
      <input type="text" v-model="type">
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
  },
  data: function(){
    return {
      isActive: true,
      hasError: false,
      activeColor: 'red',
      fontSize: 30,
      brand: 'Nike',
      type: 'Air Jordan'
    }
  },
  computed: {
    produk(){
      return this.brand+' '+this.type;
    },
    reversedProduk: function () {
      // `this` points to the vm instance
      return this.produk.split('').reverse().join('')
    }
  },
  methods:{
    changeClassName(){
      if(!this.isActive){
        this.isActive = true
      }else{
        this.isActive = false
      }
    },
    changeStyle(){
      if(this.fontSize == 30){
        this.fontSize = 24
        this.activeColor = 'green'
      }else{
        this.fontSize = 30
        this.activeColor = 'red'
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.active{color:cornflowerblue;}
</style>

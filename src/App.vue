<template>
  <div class="top"><h1>{{title}}</h1></div>
  <input type="text" ref="wow">
  <button @click="yesWow">Just Click</button>
  <button @click="showModal">Show Popup</button>
  <button @click="showModal2">Show Popup2</button>
  <div  v-if="showMod">
    <modal theme = "dark" @removeModal="showModal()">
      <h1>Good Evening</h1>
      <p>
        placeat quasi aliquam fugiat. Doloribus asperiores amet voluptatum reprehenderit!
      </p>
      <template v-slot:links>
        <a href="#">Sign Up</a>
        <a href="#">contact</a>
        <a href="#">Log in</a>
      </template>
    </modal>
  </div>
  <div v-if="showModSecond">
    <modal2 theme = "dark" @removeModal2="showModal2()">
      <h1>Good Night</h1>
      <p>
        Corem ipsum, dolor sit amet consectetur adipisicing elit. Soluta, nemo.
      </p>
      <template v-slot:likes>
        <a href="#">Food</a>
        <a href="#">Drinks</a>
      </template>
    </modal2>
  </div>
    
</template>

<script>
import Modal from './components/First.vue'  
import Modal2 from './components/Second.vue'  

export default {
  name: 'App',
  components:{Modal, Modal2},
  data() {
    return {
      title:'My first Vue application',
      header:"Sign up Here",
      two:"This is real",
      showMod:false,
      showModSecond:false
    }
  },
  methods: {
    yesWow() {
      console.log(this.$refs.wow.value);
      this.$refs.wow.classList.add("there")
      this.$refs.wow.focus()
    },
    showModal() {
      this.showMod = !this.showMod;
    },
    showModal2() {
      this.showModSecond = !this.showModSecond;
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
.top {
  height: fit-content;
  display: flex;
  justify-content: center;
  align-items: center;
}
h1 {
  border: 2px solid rgb(168, 168, 168);
  padding: 20px;
  border-radius: 10px;
  width: fit-content;
}
input {
  padding: 15px;
  margin: 5px;
  border: none;
  border-radius: 7px;
  background: rgb(218, 218, 218);
}
input:focus {
  outline: none;
  color: #ffffff;
}
button {
  width: 10px;
  border: none;
  background: #27287c;
  color: #ffffff;
  padding:10px 15px;
  width: fit-content;
  border-radius: 7px;
  cursor: pointer;
  margin: 5px;
}
p {
  margin: 10px;
}
a {
  text-decoration: none;
  color: #ffffff;
  border-radius: 11px;
  padding: 7px 10px;
  margin: 8px;
  background: #363566;
}
</style>

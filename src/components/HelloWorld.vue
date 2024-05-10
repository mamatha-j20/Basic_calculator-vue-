<template>
  <div class="main">
    <input type="text" v-model="display" readonly>
    <div class="btn1">
      <input type="button" value="C" @click="clear">
      <input type="button" value="%" @click="solve('%')">
      <input type="button" value="←" @click="back">
      <input type="button" value="/" @click="solve('/')">
    </div>
    <div class="btn">
      <input type="button" value="7" @click="solve('7')">
      <input type="button" value="8" @click="solve('8')">
      <input type="button" value="9" @click="solve('9')">
      <input type="button" value="x" @click="solve('*')">
      <br>
      <input type="button" value="4" @click="solve('4')">
      <input type="button" value="5" @click="solve('5')">
      <input type="button" value="6" @click="solve('6')">
      <input type="button" value="-" @click="solve('-')">
      <br>
      <input type="button" value="1" @click="solve('1')">
      <input type="button" value="2" @click="solve('2')">
      <input type="button" value="3" @click="solve('3')">
      <input type="button" value="+" @click="solve('+')">
      <br>
      <input type="button" value="00" @click="solve('00')">
      <input type="button" value="0" @click="solve('0')">
      <input type="button" value="." @click="solve('.')">
      <input type="button" value="=" @click="result()">
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      display: ''
    };
  },
  methods: {
    solve(val) {
      this.display += val;
    },
    result() {
      try {
        this.display = eval(this.display);
      } catch (error) {
        // Handle any errors that occur during evaluation
        console.error('An error occurred during evaluation:', error.message);
        this.display = 'Error';
      }
    },
    clear() {
      this.display = '';
    },
    back() {
      this.display = this.display.slice(0, -1);
    }
  }
};
</script>
<style scoped>
body {
  background-color: #191919;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
}

.main {
  width: 400px;
  height: 450px;
  background-color: white;
  border: 5px solid black;
  border-radius: 6px;
  margin-left: 100px;
}

input[type='text'] {
  width: 88%;
  height: 80px;
  text-align: right;
  padding: 3px 6px;
  outline: none;
  font-size: 40px;
  border: 5px solid black;
  border-radius: 6px;
  color: black;
  margin: auto;
  display: block;
}

.btn input[type='button'],
.btn1 input[type='button'] {
  width: 90px;
  height: 60px;
  padding: 2px;
  margin: 2px 0px;
  cursor: pointer;
  font-size: 18px;
  transition: 0.5s;
}

.btn input[type='button'] {
  background-color: #495250;
  color: white;
  border-radius: 6px;
}

.btn input[type='button']:hover {
  background-color: black;
}

.btn1 input[type='button'] {
  background-color: #abd151;
  color: #191919;
  border-radius: 6px;
}

.btn1 input[type='button']:hover {
  background-color: #cbed9f;
}
</style>

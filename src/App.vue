<script setup>
  import { ref } from 'vue';

  const op1 = ref('')
  const op2 = ref('')
  const actions = ['+', '-', '*', '/']
  const op = ref('+')
  const result = ref('0')

  const calc = () => {
    switch(op.value){
      case '+': result.value = Number(op1.value) + Number(op2.value)
      break

      case '-': result.value = Number(op1.value) - Number(op2.value)
      break

      case '*': result.value = Number(op1.value) * Number(op2.value)
      break

      case '/': op2.value == '0' ? result.value = 'На ноль делить нельзя!' : result.value = Number(op1.value) / Number(op2.value)
      break
    }

    
  }

</script>

<template>
  <h1>SUPER MEGA СЛАВЯНСКИЙ CALC</h1>
  <div class="container">
    <input type="text" v-model="op1" placeholder="Первый ящер">
    <select v-model="op">
      <option v-for="action in actions" :key="action">{{ action }}</option>
    </select>
    <input type="text" v-model="op2" placeholder="Второй ящер">
    <button @click="calc">посчитать убитых ящеров</button>
    <p>{{ result }}</p>
  </div>
</template>

<style>
  *{
    margin: 0;
    padding: 0;
    font-family: 'Ruslan Display', cursive;
  }
  body{
    min-height: 100vh;
    background: rgb(255,255,255);
    background: linear-gradient(180deg, rgba(255,255,255,1) 14%, rgba(9,62,121,1) 53%, rgba(255,0,104,1) 89%);
    background-repeat: no-repeat;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .container{
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 40px;
    background: #fff;
    border-radius: 15px;
    margin-top: 20px;
  }
  select{
    width: 50px;
  }
  h1{
    text-align: center;
    font-size: 50px;
  }
  button{
    background: rgb(34,195,39);
    background: linear-gradient(0deg, rgba(34,195,39,1) 0%, rgba(253,45,45,1) 100%);
    padding: 10px;
    border: none;
    border-radius: 10px;
    color: white;
  }
  input{
    background: rgb(245, 202, 202);
    padding: 10px;
    border: none;
    border-radius: 10px;
    /* color: white; */
  }
  select{
    width: 70px;
    border-radius: 10px;
    font-size: 26px;
  }
</style>

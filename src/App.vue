
<template>
  <div class="container">
    <div class="drop">
      <div class="content">
        <div class="calculator">
          <input v-model="num1" type="number" placeholder="Digite um número">
          <select v-model="operator">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
          </select>
          <input v-model="num2" type="number" placeholder="Digite um número">
          <p>Resultado: {{ result }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: "",
      num2: "",
      operator: '+'
    }
  },
  computed: {
    result() {
      switch (this.operator) {
        case '+':
        return parseInt(this.num1) + parseInt(this.num2)
        case '-':
        return parseInt(this.num1) - parseInt(this.num2)
        case '*':
        return parseInt(this.num1) * parseInt(this.num2)
        case '/':
        return parseInt(this.num1) / parseInt(this.num2)
        default:
        return 0
      }
    }
  }
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto+Condensed:ital,wght@0,300;0,400;0,700;1,300;1,400;1,700&display=swap');

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Roboto', sans-serif;
}

input{
  background-color: #f5f5f5;
  color: #333;
  margin-bottom: 8px;
  margin-top: 8px;
  
}
.container{
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}
.container .drop{
    position: relative;
    width: 450px;
    height: 450px;
    box-shadow: inset 20px 20px 20px rgba(0,0,0,0.05),
    25px 35px 20px rgba(0,0,0,0.05),
    25px 30px 30px rgba(0,0,0,0.05),
    inset -20px -20px 25px rgba(255,255,255,0.9);
    transition: 0.5s;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius:20% 80% 23% 77% / 57% 31% 69% 43%  ;
}

.container .drop:hover{
    border-radius: 50%;
}

.container .drop::before{
    content: "";
    position: absolute;
    top: 50px;
    left: 115px;
    width: 35px;
    height: 35px;
    border-radius: 50%;
    background: #fff;
    opacity: 0.9;
}

.container .drop::after{
    content: "";
    position: absolute;
    top: 90px;
    left: 110px;
    width: 15px;
    height: 15px;
    border-radius: 50%;
    background: #fff;
    opacity: 0.9;
}

.container .drop .content{
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    text-align: center;
    padding: 40px;
    margin-top: 60px;
}
.container .drop .content form{
    display: flex;
    flex-direction: column;
    gap: 20px;
    justify-content: center;
    align-items: center;
}

.container .drop .content form .inputBox{
    position: relative;
    width: 225px;
    box-shadow: inset 2px 5px 10px rgba(0,0,0,0.1),
    inset -2px -5px 10px rgba(255,255,255,1),
    15px 15px 20px rgba(0,0,0,0.05),
    15px 10px 15px rgba(0,0,0,0.025);
    border-radius: 25px;
}

.container .drop .content form .inputBox input{
    border: none;
    outline: none;
    background: transparent;
    width: 100%;
    font-size: 1em;
    padding: 10px 15px;
}
.container .drop .content form .inputBox input[type="submit"]{
color: #fff;
text-transform: uppercase;
font-size: 1em;
cursor: pointer;
letter-spacing: 0.1em;
font-weight: 500;
}

.container .drop .content form .inputBox input[type="submit"]:hover{
    color: black;
}

.container .drop .content form .inputBox:nth-child(3){
    width: 120px;
    background: rgb(255, 166, 0);
    box-shadow: inset 2px 5px 10px rgba(0,0,0,0.1),
    15px 15px 20px rgba(0,0,0,0.05),
    15px 10px 15px rgba(0,0,0,0.025);
    transition: 0.5s ease;
}

.container .drop .content form .inputBox:nth-child(3):hover{
width: 150px;
background:rgb(240, 255, 71) ;
}

#validMessage{
    color:blue;
    animation: animate 1.8s linear infinite;
    animation-delay: 0.4s;
}

@keyframes animate {
    0% {
        transform: scale(0.8);
        opacity: 0;
    }

    50% {
        transform: scale(1.1);
        opacity: 1;
    }

    100% {
        transform: scale(1.3);
        opacity: 0;
    }
}
#invalidMessage{
    color:red;
    animation: animate 1.8s linear infinite;
    animation-delay: 0.4s;
}
.calculator {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  max-width: 600px;
  margin: 0 auto;
  input, select {
    margin-right: 10px;
    padding: 10px;
    font-size: 16px;
    border-radius: 5px;
    border: none;
    background-color: #f5f5f5;
    color: #333;
  }
  
  select {
    margin-left: -10px;
  }
  
  p {
    margin-top: 10px;
    font-size: 20px;
    font-weight: bold;
  }
}
</style>
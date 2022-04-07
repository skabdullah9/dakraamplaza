<template>
  <div>
    <Calculator />
  </div>
</template>

<script>
import Calculator from './components/Calculator.vue'

export default {
  name: 'App',
  components: {
    Calculator
  },
}
</script>

<style>

 @font-face {
  font-family: 'Gilroy-Regular';
  src: url('./assets/gilroy/Gilroy-Regular.ttf') format('truetype');
  font-weight: 400;
}
 @font-face {
  font-family: 'Gilroy-Medium';
  src: url('./assets/gilroy/Gilroy-Medium.ttf') format('truetype');
  font-weight: 500;
}
@font-face {
  font-family: 'Gilroy-SemiBold';
  src: url('./assets/gilroy/Gilroy-SemiBold.ttf') format('truetype');
  font-weight: 600;
}
  @font-face {
  font-family: 'Gilroy-Bold';
  src: url('./assets/gilroy/Gilroy-Bold.ttf') format('truetype');
  font-weight: 700;
}

*,*::before,*::after {
  box-sizing: border-box;
}
body {
  margin: 0;
  font-family: 'Gilroy-Medium', sans-serif;
  color: #3A3A3A ;
}

.container {
    max-width: 1240px;
}

.font-semibold {
  font-family: 'Gilroy-SemiBold', sans-serif;
}
.font-bold {
    font-family: 'Gilroy-Bold', sans-serif;
}
.gray {
  color: #616161
}
.flex {
    display: flex;
    gap: 1rem;
}
button {
    outline: none;
    border: none;
    background: none;
    cursor: pointer;
}
button:hover,
button:focus {
  filter: brightness(110%);
}
.primary-btn {
    background-color: #FF0083;
    color: white;
}
.border-top {
   border-top: 1px solid #e4e4e4;
}


@media only screen and (max-width: 768px){

     .flex {
          gap: 0.5rem;
         flex-direction: column;
     }
}


</style>

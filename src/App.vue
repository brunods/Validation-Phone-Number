<script setup>
import TitlePrimary from './components/TitlePrimary.vue';
import Footer from './components/Footer.vue';
import InputValidate from './components/InputValidate.vue';
</script>

<template>
  <div>
    <TitlePrimary title="validar contato" />
    <InputValidate />
    <Footer author="Bruno Duarte" url_git="https://github.com/brunods" />
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  text-decoration: none;
  font-family: "Poppins", sans-serif;
}

body {
  font-family: Arial, sans-serif;
  background-color: #252525;
  color: #ffffff;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

div {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
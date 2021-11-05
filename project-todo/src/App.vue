<template>
  <div id = "app">
    <Tarefas/>
  </div>
</template>

<script>
import Tarefas from './components/Tarefa/Tarefas.vue'

export default {
  name: 'App',
  components: {
    Tarefas
  }
}
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Montserrat:400,700");

body{
  background-color: rgb(21, 8, 95);
  font-family: "Montserrat", sans-serif;
  display: grid;
  justify-items: center;
}

#app{

}

.btn_danger{
  background-color: #fc2a2a;
}

.btn{
  border: 1px solid rgb(92, 89, 89);
  padding: 10px 20px;
  cursor: pointer;
  color: #f7f8f8;
  font-weight: bold;
  border-radius: 5px;
  border-bottom: 3px solid rgb(92, 89, 89);
}

.btn:hover{
  text-shadow: 1px 1px 1px black;
  border-bottom: 1px;
  margin-top: 2px;
}

body, html {
  margin: 0;
  height: 100%;
}

table {
  margin: 0px;
  padding: 0px;
  list-style-type: none;
  width: 100%;
  border-radius: 10px;
  border-color: #afb5f5;
  background-color: #cadcf8;
}

table tr td{
  padding: 20px;
  font-size: 1.3em;
  background-color: #f7f8f8;
  margin-bottom: 2px;
  color: #3e5252;
  border-radius: 10px;
  border: 0px;
}

table thead th{
  background-color: rgb(149, 203, 221) !important;
  font-size: 1.2em;
  padding: 10px 0px;
  text-align: center !important;
  border-radius: 10px;
}

.colPequeno {
  width: 5%;
}

.card{
  margin-top:2em;
  background-color: #fff;
  box-shadow: 10px 10px 20px rgb(92, 230, 196), -8px -8px 20px rgb(32, 237, 252);
  border-radius: 10px;
  padding:15px;
  text-align: center !important;
}

</style>

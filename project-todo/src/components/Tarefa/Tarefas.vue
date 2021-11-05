<template>
  <div class="card">

    <titulo texto="Tarefas"/>

    <div style="margin-top:50px; margin-bottom:50px;">
      <input type="text" 
            placeholder="Nome da Tarefa" 
            v-model="nome"
            @keyup.enter="addTarefa()"/>
      <button class="btn btnInput" @click="addTarefa()">Adicionar</button>
    </div>

    
    <table>
      <thead>
        <th>Cod.</th>
        <th>Tarefa</th>
        <th>Opções</th>
      </thead>
      <tbody v-if="tarefas.length">
        <tr v-for="(tarefa, index) in tarefas" :key="index">
            <td><strong>{{index + 1}}</strong></td>
            <!--<td>{{tarefa.id}}</td>-->
            <td>{{tarefa.nome}}</td>
            <td>
              <button class="btn btn_danger" @click="remover(tarefa)">Remover</button>
            </td>
        </tr>
      </tbody>
      <tfoot style="text-align: center;" v-else>
        Nenhuma tarefa cadastrada.
      </tfoot>
    </table>

  </div>
</template>

<script>
import Titulo from '../_share/Titulo.vue'

export default {
  components:{
    Titulo
  },
  data(){
    return {
      titulo: "",
      nome: "",
      tarefas: [
        {id: 1, nome: "Escovar os dentes."},
      ]
    }
  },
  props: {
  },
  methods: {
    addTarefa() {

      let _tarefa = {
        nome: this.nome
      };

      this.tarefas.push(_tarefa);

      this.nome = "";
    },
    remover(tarefa){
      let indice = this.tarefas.indexOf(tarefa)
      this.tarefas.splice(indice, 1);
    }
  }
}
</script>

<style scoped>
  input {
    width: calc(100%-150px);
    border:0;
    padding: 20px;
    background-color: rgb(206, 239, 250);
    font-size: 1.3em;
    color: #687f7f;
    /*display: inline; Se fizer o display inline, não precisa fazer o calculo para o botão e o campo ficarem juntos*/
  }

  .btnInput{
    width: 150px;
    border:0px;
    padding: 20px;
    font-size: 1.3em;
    background-color: rgba(20, 84, 221, 0.822);
    display: inline;
  }

  .btnInput:hover{
    padding: 20px;
    margin: 0;
    border:0px;
  }
</style>

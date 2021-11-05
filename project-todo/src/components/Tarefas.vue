<template>
  <div class="card">
    
    <h1>{{titulo}}</h1>
    
    <input type="text" 
           placeholder="Nome da Tarefa" 
           v-model="nome"
           v-on:keyup.enter="addTarefa()"/>
    
    <table>
      <thead>
        <th>Cod.</th>
        <th>Tarefa</th>
        <th>Opções</th>
      </thead>
      <tbody>
        <tr v-for="(tarefa, index) in tarefas" :key="index">
            <td><strong>{{index + 1}}</strong></td>
            <!--<td>{{tarefa.id}}</td>-->
            <td>{{tarefa.nome}}</td>
            <td>
              <button class="btn btn_danger" @click="remover(tarefa)">Remover</button>
            </td>
        </tr>
      </tbody>
    </table>

  </div>
</template>

<script>
export default {
  data(){
    return {
      titulo: "Tarefas TODO",
      nome: "Tarefa",
      tarefas: [
        {id: 1, nome: "Tarefa 1"},
        {id: 2, nome: "Tarefa 2"},
        {id: 3, nome: "Tarefa 3"},
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

</style>

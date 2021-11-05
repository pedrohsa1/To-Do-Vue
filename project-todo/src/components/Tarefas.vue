<template>
  <div>
    
    <h1>{{titulo}}</h1>
    
    <input type="text" 
           placeholder="Nome da Tarefa" 
           v-model="nome"
           v-on:keyup.enter="addTarefa()"/>
    
    <table border="1px">
      <thead>
        <th></th>
        <th></th>
        <th></th>
      </thead>
      <tbody>
        <tr v-for="(tarefa, index) in tarefas" :key="index">
            <td>{{index + 1}}</td>
            <!--<td>{{tarefa.id}}</td>-->
            <td>{{tarefa.nome}}</td>
            <td>
              <button class="btn" @click="remover(tarefa)">Remover</button>
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
      titulo: "Tarefas TO-DO",
      nome: "Tarefa",
      tarefas: [
        {id: 1, nome: "Pedro"},
        {id: 2, nome: "Henrique"},
        {id: 3, nome: "Souza"},
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

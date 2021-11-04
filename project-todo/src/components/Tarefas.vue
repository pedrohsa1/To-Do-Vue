<template>
  <div>
    
    <h1>{{titulo}}</h1>
    
    <input type="text" placeholder="Nome da Tarefa" v-model="nome"/>
    
    <table border="1px">
      <thead>
        <th></th>
        <th></th>
        <th></th>
      </thead>
      <tbody>
        <tr>
            <td>1</td>
            <td>Alex </td>
            <td>
              <button class="btn" @click="remover()">Remover</button>
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
    }
  },
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
